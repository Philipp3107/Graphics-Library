# Table of Contents
- [What is NS](#what-is-ns)
- [Defines](#defines)

# What is NS?
NS is something that was originally calles NeXTSTEP. It combines multiple parts:
- a UNIX operating system based in the Mach kernel plus BSD
- Display PostScript and a proprietary windowing engine
- the Objective-C language and runtime
- and object-oriented (OO) application layer, including several "kist"
- development tools for the OO layers
[Wikipedia article to NS](https://en.wikipedia.org/wiki/NeXTSTEP)

# Defines
- _NS_WEAK_IMPORT : __attribute__((weak_import))
- _NS_EXPORT : __attribute__((visibility("visibility_type")))
- _NS_EXTERN  : extern "C" _NS_EXPORT -> (__attribute__((visbility("visibility_type))))
- _NS_INLINE : inline __attribute__((always_inline))
- _NS_PACKED : __attribute__((packed))
- _NS_ENUM(type, name) : enum type: name
- _NS_OPTIONS(type, name) : using name = type; enum : name
- _NS_CAST_TO_UINT(value) : static_cast<NS::UInteger>(value)
- _NS_VALIDATE_SIZE(ns, name) : static_assert(sizeof(ns::name) == sizeof(ns##name), "size mismatch " #ns :: #name)
- _NS_VALIDATE_ENUM(ns, name) : static_assert(_NS_CAST_TO_UINT(ns::name) == _NS_CAST_TO_UINT(ns##name), "value mismatch " #ns "::" #name)
