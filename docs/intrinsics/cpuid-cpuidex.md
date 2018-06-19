---
title: __cpuid，__cpuidex |Microsoft 文件
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __cpuid_cpp
- __cpuid
dev_langs:
- C++
helpviewer_keywords:
- __cpuid intrinsic
- cpuid instruction
- cpuid intrinsic
ms.assetid: f8c344d3-91bf-405f-8622-cb0e337a6bdc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 218ade95dc3e1084e42ebceda8fbfcb83c16810b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336065"
---
# <a name="cpuid-cpuidex"></a>__cpuid, __cpuidex

**Microsoft 特定的**

產生可在 x86 和 `cpuid` 上使用的 [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] 指令。 此指令會查詢處理器，以取得受支援功能及 CPU 類型的相關資訊。

## <a name="syntax"></a>語法

```cpp
void __cpuid(
   int cpuInfo[4],
   int function_id
);

void __cpuidex(
   int cpuInfo[4],
   int function_id,
   int subfunction_id
);
```

### <a name="parameters"></a>參數

[out]*cpuInfo*<br/>
四個整數的陣列，包含 EAX、EBX、ECX 及 EDX 中傳回之受支援 CPU 功能的相關資訊。

[in]*function_id*<br/>
指定要擷取之資訊的程式碼，在 EAX 中傳遞。

[in]*subfunction_id*<br/>
指定要擷取之資訊的其他程式碼，在 ECX 中傳遞。

## <a name="requirements"></a>需求

|內建|架構|
|---------------|------------------|
|`__cpuid`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|
|`__cpuidex`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|

**標頭檔** \<intrin.h >

## <a name="remarks"></a>備註

此內建物件會儲存支援的功能和所傳回的 CPU 資訊`cpuid`中的指示*cpuInfo*，四個 32 位元整數的填滿具有值的陣列的 EAX、 EBX、 ECX 及 EDX 暫存器 （在中，順序）。 傳回的資訊有不同的意義，做為傳遞的值而定*function_id*參數。 使用的各種值傳回的資訊*function_id*因處理器而異。

`__cpuid` 內建物件會在呼叫 `cpuid` 指令之前，清除 ECX 暫存器。 `__cpuidex`內建函式設定的 ECX 暫存器值*subfunction_id*之前它會產生`cpuid`指令。 這可讓您收集處理器的其他資訊。

如需使用和傳回值的這些內建的 Intel 處理器上的特定參數的詳細資訊，請參閱文件`cpuid`中的指示[Intel 64 和 ia-32 架構軟體開發人員手冊磁碟區 2： 指令集參考](http://go.microsoft.com/fwlink/p/?LinkID=510021)和[Intel 架構指令集延伸程式設計參考](http://go.microsoft.com/fwlink/p/?LinkID=506627)。 Intel 文件會使用詞彙 「 分葉 」 與 「 對 「 *function_id*和*subfunction_id*在 EAX 和 ECX 中傳遞的參數。

如需使用和 AMD 處理器這些內建函式傳回的值的特定參數的詳細資訊，請參閱文件`cpuid`AMD64 架構程式設計人員手動磁碟區 3 中的指示： 一般用途和系統指示，和特定處理器系列的修訂指南中。 如需這些文件和其他資訊的連結，請參閱 AMD[開發人員指南、 手冊與 ISA 文件](http://go.microsoft.com/fwlink/p/?LinkId=510023)頁面。 AMD 文件使用詞彙 「 函式號碼 」 和 「 子函式號碼 」 進行*function_id*和*subfunction_id*在 EAX 和 ECX 中傳遞的參數。

當*function_id*引數為 0， *cpuInfo*[0] 傳回最高可用非擴充*function_id*處理器所支援的值。 處理器製造商編碼在*cpuInfo*[1]， *cpuInfo*[2]，和*cpuInfo*[3]。

支援對特定指令集擴充功能和 CPU 功能會編碼在*cpuInfo*更高版本傳回的結果*function_id*值。 如需詳細資訊，請參閱上述連結的手冊，和下列範例程式碼。

部分處理器支援擴充功能 CPUID 資訊。 如果這支援， *function_id*從 0x80000000 開始的值可能會用來傳回資訊。 若要判斷所允許的最大有意義的值，設定*function_id*為 0x80000000。 最大值*function_id*支援擴充函式寫入*cpuInfo*[0]。

## <a name="example"></a>範例

本範例示範可透過 `__cpuid` 和 `__cpuidex` 內建函式取得的一些資訊。 應用程式會列出目前的處理器所支援的指令集擴充功能。 輸出會顯示特定處理器的可能結果。

```cpp
// InstructionSet.cpp
// Compile by using: cl /EHsc /W4 InstructionSet.cpp
// processor: x86, x64
// Uses the __cpuid intrinsic to get information about
// CPU extended instruction set support.

#include <iostream>
#include <vector>
#include <bitset>
#include <array>
#include <string>
#include <intrin.h>

class InstructionSet
{
    // forward declarations
    class InstructionSet_Internal;

public:
    // getters
    static std::string Vendor(void) { return CPU_Rep.vendor_; }
    static std::string Brand(void) { return CPU_Rep.brand_; }

    static bool SSE3(void) { return CPU_Rep.f_1_ECX_[0]; }
    static bool PCLMULQDQ(void) { return CPU_Rep.f_1_ECX_[1]; }
    static bool MONITOR(void) { return CPU_Rep.f_1_ECX_[3]; }
    static bool SSSE3(void) { return CPU_Rep.f_1_ECX_[9]; }
    static bool FMA(void) { return CPU_Rep.f_1_ECX_[12]; }
    static bool CMPXCHG16B(void) { return CPU_Rep.f_1_ECX_[13]; }
    static bool SSE41(void) { return CPU_Rep.f_1_ECX_[19]; }
    static bool SSE42(void) { return CPU_Rep.f_1_ECX_[20]; }
    static bool MOVBE(void) { return CPU_Rep.f_1_ECX_[22]; }
    static bool POPCNT(void) { return CPU_Rep.f_1_ECX_[23]; }
    static bool AES(void) { return CPU_Rep.f_1_ECX_[25]; }
    static bool XSAVE(void) { return CPU_Rep.f_1_ECX_[26]; }
    static bool OSXSAVE(void) { return CPU_Rep.f_1_ECX_[27]; }
    static bool AVX(void) { return CPU_Rep.f_1_ECX_[28]; }
    static bool F16C(void) { return CPU_Rep.f_1_ECX_[29]; }
    static bool RDRAND(void) { return CPU_Rep.f_1_ECX_[30]; }

    static bool MSR(void) { return CPU_Rep.f_1_EDX_[5]; }
    static bool CX8(void) { return CPU_Rep.f_1_EDX_[8]; }
    static bool SEP(void) { return CPU_Rep.f_1_EDX_[11]; }
    static bool CMOV(void) { return CPU_Rep.f_1_EDX_[15]; }
    static bool CLFSH(void) { return CPU_Rep.f_1_EDX_[19]; }
    static bool MMX(void) { return CPU_Rep.f_1_EDX_[23]; }
    static bool FXSR(void) { return CPU_Rep.f_1_EDX_[24]; }
    static bool SSE(void) { return CPU_Rep.f_1_EDX_[25]; }
    static bool SSE2(void) { return CPU_Rep.f_1_EDX_[26]; }

    static bool FSGSBASE(void) { return CPU_Rep.f_7_EBX_[0]; }
    static bool BMI1(void) { return CPU_Rep.f_7_EBX_[3]; }
    static bool HLE(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_7_EBX_[4]; }
    static bool AVX2(void) { return CPU_Rep.f_7_EBX_[5]; }
    static bool BMI2(void) { return CPU_Rep.f_7_EBX_[8]; }
    static bool ERMS(void) { return CPU_Rep.f_7_EBX_[9]; }
    static bool INVPCID(void) { return CPU_Rep.f_7_EBX_[10]; }
    static bool RTM(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_7_EBX_[11]; }
    static bool AVX512F(void) { return CPU_Rep.f_7_EBX_[16]; }
    static bool RDSEED(void) { return CPU_Rep.f_7_EBX_[18]; }
    static bool ADX(void) { return CPU_Rep.f_7_EBX_[19]; }
    static bool AVX512PF(void) { return CPU_Rep.f_7_EBX_[26]; }
    static bool AVX512ER(void) { return CPU_Rep.f_7_EBX_[27]; }
    static bool AVX512CD(void) { return CPU_Rep.f_7_EBX_[28]; }
    static bool SHA(void) { return CPU_Rep.f_7_EBX_[29]; }

    static bool PREFETCHWT1(void) { return CPU_Rep.f_7_ECX_[0]; }

    static bool LAHF(void) { return CPU_Rep.f_81_ECX_[0]; }
    static bool LZCNT(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_81_ECX_[5]; }
    static bool ABM(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[5]; }
    static bool SSE4a(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[6]; }
    static bool XOP(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[11]; }
    static bool TBM(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[21]; }

    static bool SYSCALL(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_81_EDX_[11]; }
    static bool MMXEXT(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_EDX_[22]; }
    static bool RDTSCP(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_81_EDX_[27]; }
    static bool _3DNOWEXT(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_EDX_[30]; }
    static bool _3DNOW(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_EDX_[31]; }

private:
    static const InstructionSet_Internal CPU_Rep;

    class InstructionSet_Internal
    {
    public:
        InstructionSet_Internal()
            : nIds_{ 0 },
            nExIds_{ 0 },
            isIntel_{ false },
            isAMD_{ false },
            f_1_ECX_{ 0 },
            f_1_EDX_{ 0 },
            f_7_EBX_{ 0 },
            f_7_ECX_{ 0 },
            f_81_ECX_{ 0 },
            f_81_EDX_{ 0 },
            data_{},
            extdata_{}
        {
            //int cpuInfo[4] = {-1};
            std::array<int, 4> cpui;

            // Calling __cpuid with 0x0 as the function_id argument
            // gets the number of the highest valid function ID.
            __cpuid(cpui.data(), 0);
            nIds_ = cpui[0];

            for (int i = 0; i <= nIds_; ++i)
            {
                __cpuidex(cpui.data(), i, 0);
                data_.push_back(cpui);
            }

            // Capture vendor string
            char vendor[0x20];
            memset(vendor, 0, sizeof(vendor));
            *reinterpret_cast<int*>(vendor) = data_[0][1];
            *reinterpret_cast<int*>(vendor + 4) = data_[0][3];
            *reinterpret_cast<int*>(vendor + 8) = data_[0][2];
            vendor_ = vendor;
            if (vendor_ == "GenuineIntel")
            {
                isIntel_ = true;
            }
            else if (vendor_ == "AuthenticAMD")
            {
                isAMD_ = true;
            }

            // load bitset with flags for function 0x00000001
            if (nIds_ >= 1)
            {
                f_1_ECX_ = data_[1][2];
                f_1_EDX_ = data_[1][3];
            }

            // load bitset with flags for function 0x00000007
            if (nIds_ >= 7)
            {
                f_7_EBX_ = data_[7][1];
                f_7_ECX_ = data_[7][2];
            }

            // Calling __cpuid with 0x80000000 as the function_id argument
            // gets the number of the highest valid extended ID.
            __cpuid(cpui.data(), 0x80000000);
            nExIds_ = cpui[0];

            char brand[0x40];
            memset(brand, 0, sizeof(brand));

            for (int i = 0x80000000; i <= nExIds_; ++i)
            {
                __cpuidex(cpui.data(), i, 0);
                extdata_.push_back(cpui);
            }

            // load bitset with flags for function 0x80000001
            if (nExIds_ >= 0x80000001)
            {
                f_81_ECX_ = extdata_[1][2];
                f_81_EDX_ = extdata_[1][3];
            }

            // Interpret CPU brand string if reported
            if (nExIds_ >= 0x80000004)
            {
                memcpy(brand, extdata_[2].data(), sizeof(cpui));
                memcpy(brand + 16, extdata_[3].data(), sizeof(cpui));
                memcpy(brand + 32, extdata_[4].data(), sizeof(cpui));
                brand_ = brand;
            }
        };

        int nIds_;
        int nExIds_;
        std::string vendor_;
        std::string brand_;
        bool isIntel_;
        bool isAMD_;
        std::bitset<32> f_1_ECX_;
        std::bitset<32> f_1_EDX_;
        std::bitset<32> f_7_EBX_;
        std::bitset<32> f_7_ECX_;
        std::bitset<32> f_81_ECX_;
        std::bitset<32> f_81_EDX_;
        std::vector<std::array<int, 4>> data_;
        std::vector<std::array<int, 4>> extdata_;
    };
};

// Initialize static member data
const InstructionSet::InstructionSet_Internal InstructionSet::CPU_Rep;

// Print out supported instruction set extensions
int main()
{
    auto& outstream = std::cout;

    auto support_message = [&outstream](std::string isa_feature, bool is_supported) {
        outstream << isa_feature << (is_supported ? " supported" : " not supported") << std::endl;
    };

    std::cout << InstructionSet::Vendor() << std::endl;
    std::cout << InstructionSet::Brand() << std::endl;

    support_message("3DNOW",       InstructionSet::_3DNOW());
    support_message("3DNOWEXT",    InstructionSet::_3DNOWEXT());
    support_message("ABM",         InstructionSet::ABM());
    support_message("ADX",         InstructionSet::ADX());
    support_message("AES",         InstructionSet::AES());
    support_message("AVX",         InstructionSet::AVX());
    support_message("AVX2",        InstructionSet::AVX2());
    support_message("AVX512CD",    InstructionSet::AVX512CD());
    support_message("AVX512ER",    InstructionSet::AVX512ER());
    support_message("AVX512F",     InstructionSet::AVX512F());
    support_message("AVX512PF",    InstructionSet::AVX512PF());
    support_message("BMI1",        InstructionSet::BMI1());
    support_message("BMI2",        InstructionSet::BMI2());
    support_message("CLFSH",       InstructionSet::CLFSH());
    support_message("CMPXCHG16B",  InstructionSet::CMPXCHG16B());
    support_message("CX8",         InstructionSet::CX8());
    support_message("ERMS",        InstructionSet::ERMS());
    support_message("F16C",        InstructionSet::F16C());
    support_message("FMA",         InstructionSet::FMA());
    support_message("FSGSBASE",    InstructionSet::FSGSBASE());
    support_message("FXSR",        InstructionSet::FXSR());
    support_message("HLE",         InstructionSet::HLE());
    support_message("INVPCID",     InstructionSet::INVPCID());
    support_message("LAHF",        InstructionSet::LAHF());
    support_message("LZCNT",       InstructionSet::LZCNT());
    support_message("MMX",         InstructionSet::MMX());
    support_message("MMXEXT",      InstructionSet::MMXEXT());
    support_message("MONITOR",     InstructionSet::MONITOR());
    support_message("MOVBE",       InstructionSet::MOVBE());
    support_message("MSR",         InstructionSet::MSR());
    support_message("OSXSAVE",     InstructionSet::OSXSAVE());
    support_message("PCLMULQDQ",   InstructionSet::PCLMULQDQ());
    support_message("POPCNT",      InstructionSet::POPCNT());
    support_message("PREFETCHWT1", InstructionSet::PREFETCHWT1());
    support_message("RDRAND",      InstructionSet::RDRAND());
    support_message("RDSEED",      InstructionSet::RDSEED());
    support_message("RDTSCP",      InstructionSet::RDTSCP());
    support_message("RTM",         InstructionSet::RTM());
    support_message("SEP",         InstructionSet::SEP());
    support_message("SHA",         InstructionSet::SHA());
    support_message("SSE",         InstructionSet::SSE());
    support_message("SSE2",        InstructionSet::SSE2());
    support_message("SSE3",        InstructionSet::SSE3());
    support_message("SSE4.1",      InstructionSet::SSE41());
    support_message("SSE4.2",      InstructionSet::SSE42());
    support_message("SSE4a",       InstructionSet::SSE4a());
    support_message("SSSE3",       InstructionSet::SSSE3());
    support_message("SYSCALL",     InstructionSet::SYSCALL());
    support_message("TBM",         InstructionSet::TBM());
    support_message("XOP",         InstructionSet::XOP());
    support_message("XSAVE",       InstructionSet::XSAVE());
}
```

```Output
GenuineIntel
        Intel(R) Core(TM) i5-2500 CPU @ 3.30GHz
3DNOW not supported
3DNOWEXT not supported
ABM not supported
ADX not supported
AES supported
AVX supported
AVX2 not supported
AVX512CD not supported
AVX512ER not supported
AVX512F not supported
AVX512PF not supported
BMI1 not supported
BMI2 not supported
CLFSH supported
CMPXCHG16B supported
CX8 supported
ERMS not supported
F16C not supported
FMA not supported
FSGSBASE not supported
FXSR supported
HLE not supported
INVPCID not supported
LAHF supported
LZCNT not supported
MMX supported
MMXEXT not supported
MONITOR not supported
MOVBE not supported
MSR supported
OSXSAVE supported
PCLMULQDQ supported
POPCNT supported
PREFETCHWT1 not supported
RDRAND not supported
RDSEED not supported
RDTSCP supported
RTM not supported
SEP supported
SHA not supported
SSE supported
SSE2 supported
SSE3 supported
SSE4.1 supported
SSE4.2 supported
SSE4a not supported
SSSE3 supported
SYSCALL supported
TBM not supported
XOP not supported
XSAVE supported

```

**結束 Microsoft 特定的**

## <a name="see-also"></a>另請參閱

[編譯器內建](../intrinsics/compiler-intrinsics.md)
