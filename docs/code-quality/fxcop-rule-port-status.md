---
title: FxCop 规则端口状态
ms.date: 05/21/2019
ms.topic: reference
helpviewer_keywords:
- fxcop rules
- fxcop analyzers, ported rules
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 0d78e7dcd7dfd203a15510037b277b8c2633805e
ms.sourcegitcommit: cd21b38eefdea2cdefb53e68e7a30b868e78dd6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "66038643"
---
# <a name="fxcop-rule-port-status"></a>Fxcop 规则端口状态

如果你以前在 Visual Studio 的早期版本中使用静态代码分析，您可能想知道哪些这些规则作为当前实现中可用[FxCop 分析器](install-fxcop-analyzers.md)。 此页列出了和尚未移植移植的规则以及是否有计划其移植。

## <a name="ported-rules"></a>移植的规则

[自动生成文档页](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md)roslyn 分析器在存储库具有已经移植到 FxCop 分析器的规则的最新列表。 该页面还具有其他信息，如是否默认情况下启用规则，以及它有一个关联*代码修补程序*。 ([代码修补程序](../ide/quick-actions.md)是一次单击修复 Visual Studio 中的灯泡图标菜单中可用。)

截至此页上，列表的 FxCop 规则已经移植到[FxCop 分析器](install-fxcop-analyzers.md)包括：

规则 ID | 标题
--------|---------
[CA1000](ca1000-do-not-declare-static-members-on-generic-types.md) | 不要在泛型类型中声明静态成员
[CA1001](ca1001-types-that-own-disposable-fields-should-be-disposable.md) | 具有可释放字段的类型应该是可释放的
[CA1003](ca1003-use-generic-event-handler-instances.md) | 使用泛型事件处理程序实例
[CA1008](ca1008-enums-should-have-zero-value.md) | 枚举应具有零值
[CA1010](ca1010-collections-should-implement-generic-interface.md) | 集合应实现泛型接口
[CA1012](ca1012-abstract-types-should-not-have-constructors.md) | 抽象类型不应具有构造函数
[CA1014](ca1014-mark-assemblies-with-clscompliantattribute.md) | 用 CLSCompliant 标记程序集
[CA1016](ca1016-mark-assemblies-with-assemblyversionattribute.md) | 用程序集版本标记程序集
[CA1017](ca1017-mark-assemblies-with-comvisibleattribute.md) | 用 ComVisible 标记程序集
[CA1018](ca1018-mark-attributes-with-attributeusageattribute.md) | 用 AttributeUsageAttribute 标记特性
[CA1019](ca1019-define-accessors-for-attribute-arguments.md) | 定义特性参数的访问器
[CA1024](ca1024-use-properties-where-appropriate.md) | 在适用处使用属性
[CA1027](ca1027-mark-enums-with-flagsattribute.md) | 用 FlagsAttribute 标记枚举
[CA1028](ca1028-enum-storage-should-be-int32.md) | 枚举存储应为 Int32
[CA1030](ca1030-use-events-where-appropriate.md) | 在适用处使用事件
[CA1031](ca1031-do-not-catch-general-exception-types.md) | 不要捕捉一般异常类型
[CA1032](ca1032-implement-standard-exception-constructors.md) | 实现标准异常构造函数
[CA1033](ca1033-interface-methods-should-be-callable-by-child-types.md) | 接口方法应可由子类型调用
[CA1034](ca1034-nested-types-should-not-be-visible.md) | 嵌套类型不应是可见的
[CA1036](ca1036-override-methods-on-comparable-types.md) | 重写可比较类型中的方法
[CA1040](ca1040-avoid-empty-interfaces.md) | 避免使用空接口
[CA1041](ca1041-provide-obsoleteattribute-message.md) | 提供 ObsoleteAttribute 消息
[CA1043](ca1043-use-integral-or-string-argument-for-indexers.md) | 使用整型或字符串参数用于索引器
[CA1044](ca1044-properties-should-not-be-write-only.md) | 属性不应是只写的
[CA1050](ca1050-declare-types-in-namespaces.md) | 在命名空间中声明类型
[CA1051](ca1051-do-not-declare-visible-instance-fields.md) | 不要声明可见实例字段
[CA1052](ca1052-static-holder-types-should-be-sealed.md) | 静态容器类型应为静态或 NotInheritable （请参阅此表后面的注释）
[CA1053](ca1053-static-holder-types-should-not-have-constructors.md) | 静态容器类型不应具有构造函数 （请参阅此表后面的注释）
[CA1054](ca1054-uri-parameters-should-not-be-strings.md) | Uri 参数不应为字符串
[CA1055](ca1055-uri-return-values-should-not-be-strings.md) | Uri 返回值不应为字符串
[CA1056](ca1056-uri-properties-should-not-be-strings.md) | Uri 属性不应为字符串
[CA1058](ca1058-types-should-not-extend-certain-base-types.md) | 类型不应扩展某些基类型
[CA1060](ca1060-move-p-invokes-to-nativemethods-class.md) | 将 pinvoke 移至本机方法类
[CA1061](ca1061-do-not-hide-base-class-methods.md) | 不要隐藏基类方法
[CA1062](ca1062-validate-arguments-of-public-methods.md) | 验证公共方法的参数
[CA1063](ca1063-implement-idisposable-correctly.md) | 正确实现 IDisposable
[CA1064](ca1064-exceptions-should-be-public.md) | 异常应该是公共的
[CA1065](ca1065-do-not-raise-exceptions-in-unexpected-locations.md) | 不要在意外的位置引发异常
CA1066 | 类型{0}应实现 IEquatable<T>因为它会覆盖 Equals
CA1067 | 实现 IEquatable 时重写 Object.Equals(object)<T>
CA1068 | CancellationToken 参数必须放在最后
CA1200 | 避免使用带前缀的 cref 标记
[CA1303](ca1303-do-not-pass-literals-as-localized-parameters.md) | 请不要将文本作为本地化参数传递
[CA1304](ca1304-specify-cultureinfo.md) | 指定 CultureInfo
[CA1305](ca1305-specify-iformatprovider.md) | 指定 IFormatProvider
[CA1307](ca1307-specify-stringcomparison.md) | 指定 StringComparison
[CA1308](ca1308-normalize-strings-to-uppercase.md) | 将字符串规范化为大写
[CA1309](ca1309-use-ordinal-stringcomparison.md) | 使用序号字符串比较
[CA1401](ca1401-p-invokes-should-not-be-visible.md) | P/Invokes 应该是不可见的
[CA1501](ca1501-avoid-excessive-inheritance.md) | 避免过度继承
[CA1502](ca1502-avoid-excessive-complexity.md) | 避免过度复杂
[CA1505](ca1505-avoid-unmaintainable-code.md) | 避免使用无法维护的代码
[CA1506](ca1506-avoid-excessive-class-coupling.md) | 避免过度类耦合度
[CA1507](ca1507.md) | 使用 nameof 来表示符号名
CA1508 | 避免死条件代码
CA1509 | 代码度量值规则规范文件中的无效条目
[CA1707](ca1707-identifiers-should-not-contain-underscores.md) | 标识符不应包含下划线
[CA1708](ca1708-identifiers-should-differ-by-more-than-case.md) | 标识符应以大小写之外的差别进行区分
[CA1710](ca1710-identifiers-should-have-correct-suffix.md) | 标识符应具有正确的后缀
[CA1711](ca1711-identifiers-should-not-have-incorrect-suffix.md) | 标识符应采用正确的后缀
[CA1712](ca1712-do-not-prefix-enum-values-with-type-name.md) | 不要将类型名用作枚举值的前缀
[CA1714](ca1714-flags-enums-should-have-plural-names.md) | Flags 枚举应采用复数形式的名称
[CA1715](ca1715-identifiers-should-have-correct-prefix.md) | 标识符应具有正确的前缀
[CA1716](ca1716-identifiers-should-not-match-keywords.md) | 标识符不应与关键字冲突
[CA1717](ca1717-only-flagsattribute-enums-should-have-plural-names.md) | 只有 FlagsAttribute 枚举应采用复数形式的名称
[CA1720](ca1720-identifiers-should-not-contain-type-names.md) | 标识符包含类型名称
[CA1721](ca1721-property-names-should-not-match-get-methods.md) | 属性名不应与 get 方法冲突
[CA1724](ca1724-type-names-should-not-match-namespaces.md) | 类型名不应与命名空间
[CA1725](ca1725-parameter-names-should-match-base-declaration.md) | 参数名应与基方法中的声明保持一致
[CA1801](ca1801-review-unused-parameters.md) | 检查未使用的参数
[CA1802](ca1802-use-literals-where-appropriate.md) | 在适用处使用文本
[CA1806](ca1806-do-not-ignore-method-results.md) | 不要忽略方法结果
[CA1810](ca1810-initialize-reference-type-static-fields-inline.md) | 以内联方式初始化引用类型的静态字段
[CA1812](ca1812-avoid-uninstantiated-internal-classes.md) | 避免未实例化的内部类
[CA1813](ca1813-avoid-unsealed-attributes.md) | 避免使用非密封特性
[CA1814](ca1814-prefer-jagged-arrays-over-multidimensional.md) | 与多维数组相比，首选使用交错数组
[CA1815](ca1815-override-equals-and-operator-equals-on-value-types.md) | 重写值类型上的 Equals 和相等运算符
[CA1816](ca1816-call-gc-suppressfinalize-correctly.md) | Dispose 方法应调用 SuppressFinalize
[CA1819](ca1819-properties-should-not-return-arrays.md) | 属性不应返回数组
[CA1820](ca1820-test-for-empty-strings-using-string-length.md) | 使用字符串长度测试是否有空字符串
[CA1821](ca1821-remove-empty-finalizers.md) | 移除空终结器
[CA1822](ca1822-mark-members-as-static.md) | 将成员标记为 static
[CA1823](ca1823-avoid-unused-private-fields.md) | 避免未使用的私有字段
[CA1824](ca1824-mark-assemblies-with-neutralresourceslanguageattribute.md) | 用 NeutralResourcesLanguageAttribute 标记程序集
CA1825 | 避免零长度数组分配。
CA1826 | 不要使用可编制索引的集合上的可枚举的方法。 而是直接使用集合
[CA2000](ca2000-dispose-objects-before-losing-scope.md) | 丢失范围之前释放对象
[CA2002](ca2002-do-not-lock-on-objects-with-weak-identity.md) | 不要锁定具有弱标识的对象
[CA2007](ca2007-do-not-directly-await-task.md) | 请考虑在等待的任务上调用 ConfigureAwait
CA2008 | 不要创建任务而无需传递 TaskScheduler
CA2009 | 不要调用 ToImmutableCollection ImmutableCollection 值
CA2010 | 始终使用由 PreserveSigAttribute 使用标记的方法返回的值
[CA2100](ca2100-review-sql-queries-for-security-vulnerabilities.md) | 检查 SQL 查询是否存在安全漏洞
[CA2101](ca2101-specify-marshaling-for-p-invoke-string-arguments.md) | 指定对 P/Invoke 字符串参数进行封送处理
[CA2119](ca2119-seal-methods-that-satisfy-private-interfaces.md) | 密封满足私有接口的方法
[CA2153](ca2153-avoid-handling-corrupted-state-exceptions.md) | 请勿捕获损坏状态异常
[CA2200](ca2200-rethrow-to-preserve-stack-details.md) | 再次引发以保留堆栈详细信息。
[CA2201](ca2201-do-not-raise-reserved-exception-types.md) | 不要引发保留的异常类型
[CA2207](ca2207-initialize-value-type-static-fields-inline.md) | 以内联方式初始化值类型的静态字段
[CA2208](ca2208-instantiate-argument-exceptions-correctly.md) | 正确实例化参数异常
[CA2211](ca2211-non-constant-fields-should-not-be-visible.md) | 非常量字段不应是可见的
[CA2213](ca2213-disposable-fields-should-be-disposed.md) | 应释放可释放的字段
[CA2214](ca2214-do-not-call-overridable-methods-in-constructors.md) | 不要在构造函数中调用可重写的方法
[CA2216](ca2216-disposable-types-should-declare-finalizer.md) | 可释放类型应声明终结器
[CA2217](ca2217-do-not-mark-enums-with-flagsattribute.md) | 不要使用 FlagsAttribute 标记枚举
[CA2218](ca2218-override-gethashcode-on-overriding-equals.md) | 重写 Equals 时重写 GetHashCode
[CA2219](ca2219-do-not-raise-exceptions-in-exception-clauses.md) | 不会引发 finally 子句中的异常
[CA2224](ca2224-override-equals-on-overloading-operator-equals.md) | 重载运算符时重写 Equals 等于
[CA2225](ca2225-operator-overloads-have-named-alternates.md) | 运算符重载具有命名的备用项
[CA2226](ca2226-operators-should-have-symmetrical-overloads.md) | 运算符应有对称重载
[CA2227](ca2227-collection-properties-should-be-read-only.md) | 集合属性应为只读
[CA2229](ca2229-implement-serialization-constructors.md) | 实现序列化构造函数
[CA2231](ca2231-overload-operator-equals-on-overriding-valuetype-equals.md) | 重写值的相等运算符重载键入等号
[CA2234](ca2234-pass-system-uri-objects-instead-of-strings.md) | 传递系统而不是字符串的 uri 对象
[CA2235](ca2235-mark-all-non-serializable-fields.md) | 标记所有不可序列化的字段
[CA2237](ca2237-mark-iserializable-types-with-serializableattribute.md) | 用 serializable 标记 ISerializable 类型
[CA2241](ca2241-provide-correct-arguments-to-formatting-methods.md) | 为格式化方法提供正确的参数
[CA2242](ca2242-test-for-nan-correctly.md) | 正确测试 NaN
[CA2243](ca2243-attribute-string-literals-should-parse-correctly.md) | 特性字符串文本应正确分析
CA2244 | 不重复索引的元素的初始化
[CA2300](ca2300-do-not-use-insecure-deserializer-binaryformatter.md) | 请勿使用不安全的反序列化程序 BinaryFormatte
[CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) | 在未先设置 BinaryFormatter.Binder 的情况下，请不要调用 BinaryFormatter.Deserialize
[CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md) | 在调用 BinaryFormatter.Deserialize 之前，确保设置 BinaryFormatter.Binder
[CA2305](ca2305-do-not-use-insecure-deserializer-losformatter.md) | 请勿使用不安全的反序列化程序 LosFormatter
[CA2310](ca2310-do-not-use-insecure-deserializer-netdatacontractserializer.md) | 请勿使用不安全的反序列化程序 NetDataContractSerializer
[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) | 在未先设置 NetDataContractSerializer.Binder 的情况下，请不要反序列化
[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md) | 确保在反序列化之前设置 NetDataContractSerializer.Binder
[CA2315](ca2315-do-not-use-insecure-deserializer-objectstateformatter.md) | 请勿使用不安全的反序列化程序 ObjectStateFormatter
[CA2321](ca2321.md) | 请勿使用 SimpleTypeResolver 对 JavaScriptSerializer 进行反序列化
[CA2322](ca2322.md) | 确保在反序列化之前没有使用 SimpleTypeResolver 初始化 JavaScriptSerializer
[CA3001](ca3001-review-code-for-sql-injection-vulnerabilities.md) | 查看 SQL 注入漏洞的代码
[CA3002](ca3002-review-code-for-xss-vulnerabilities.md) | 查看 XSS 漏洞的代码
[CA3003](ca3003-review-code-for-file-path-injection-vulnerabilities.md) | 查看文件路径注入漏洞的代码
[CA3004](ca3004-review-code-for-information-disclosure-vulnerabilities.md) | 查看信息泄露漏洞的代码
[CA3005](ca3005-review-code-for-ldap-injection-vulnerabilities.md) | 查看 LDAP 注入漏洞的代码
[CA3006](ca3006-review-code-for-process-command-injection-vulnerabilities.md) | 查看进程命令注入漏洞的代码
[CA3007](ca3007-review-code-for-open-redirect-vulnerabilities.md) | 查看公开重定向漏洞的代码
[CA3008](ca3008-review-code-for-xpath-injection-vulnerabilities.md) | 查看 XPath 注入漏洞的代码
[CA3009](ca3009-review-code-for-xml-injection-vulnerabilities.md) | 查看 XML 注入漏洞的代码
[CA3010](ca3010-review-code-for-xaml-injection-vulnerabilities.md) | 查看 XAML 注入漏洞的代码
[CA3011](ca3011-review-code-for-dll-injection-vulnerabilities.md) | 查看 DLL 注入漏洞的代码
[CA3012](ca3012-review-code-for-regex-injection-vulnerabilities.md) | 查看正则表达式注入漏洞的代码
CA3061 | 未添加的 URL 的架构
[CA3075](ca3075-insecure-dtd-processing.md) | XML 中不安全的 DTD 处理
[CA3076](ca3076-insecure-xslt-script-execution.md) | 不安全的 XSLT 脚本处理。
[CA3077](ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader.md) | 在 API 设计、 XmlDocument 和 XmlTextReader 的不安全处理
[CA3147](ca3147-mark-verb-handlers-with-validateantiforgerytoken.md) | Mark 谓词使用的处理程序验证防伪令牌
[CA5350](ca5350-do-not-use-weak-cryptographic-algorithms.md) | 请勿使用弱加密算法
[CA5351](ca5351-do-not-use-broken-cryptographic-algorithms.md) | 不使用损坏的加密算法
CA5358 | 不要使用不安全的密码模式
CA5359 | 不要禁用证书验证
CA5360 | 不要在反序列化调用危险的方法
CA5361 | 不禁用 SChannel 使用较强的加密
CA5362 | 未引用自身可序列化的类中
CA5363 | 不要禁用请求验证
CA5364 | 不要使用不推荐使用的安全协议
CA5365 | 不要禁用检查 HTTP 标头
CA5366 | 用于数据集读取 Xml 的 XmlReader
CA5367 | 不序列化类型和指针字段
CA5368 | 从页派生的类集 ViewStateUserKey
CA5369 | 使用 XmlReader 进行反序列化
CA5370 | 使用 XmlReader 验证读取器
CA5371 | 使用 XmlReader 进行架构读取
CA5372 | 使用 XPathDocument XmlReader
CA5373 | 不要使用过时的密钥派生函数
CA5374 | 不使用 XslTransform
CA5375 | 不使用帐户共享的访问签名
CA5376 | 使用 SharedAccessProtocol HttpsOnly
CA5377 | 使用容器级访问策略
CA5378 | 不要禁用 ServicePointManagerSecurityProtocols
CA5379 | 请勿使用弱密钥派生函数算法
CA9999 | 分析工具版本不匹配

> [!NOTE]
> 规则 CA1052 和从原始的 FxCop 实现 CA1053 组合成一条规则，CA1052，FxCop 分析器中。

## <a name="unported-rules"></a>Unported 的规则

尚未移植到的规则集[FxCop 分析器](install-fxcop-analyzers.md)包含规则的尚未，但仍[可能移植](#rules-that-may-be-ported)，以及不推荐使用和[将无法移植的](#deprecated-rules).

### <a name="rules-that-may-be-ported"></a>可移植的规则

以下 FxCop 静态代码分析规则尚未被实现为分析器，但仍可能。 这可能是由于一个阻塞的技术原因或只是该规则是较低的优先级。 每个规则的迁移状态的详细信息，请单击中的链接**跟踪问题**列。

规则 ID | 跟踪问题
--- | ---
[CA1002](ca1002-do-not-expose-generic-lists.md) | [https://github.com/dotnet/roslyn-analyzers/issues/369](https://github.com/dotnet/roslyn-analyzers/issues/369)
[CA1004](ca1004-generic-methods-should-provide-type-parameter.md) | [https://github.com/dotnet/roslyn-analyzers/issues/370](https://github.com/dotnet/roslyn-analyzers/issues/370)
[CA1005](ca1005-avoid-excessive-parameters-on-generic-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/371](https://github.com/dotnet/roslyn-analyzers/issues/371)
[CA1006](ca1006-do-not-nest-generic-types-in-member-signatures.md) | [https://github.com/dotnet/roslyn-analyzers/issues/372](https://github.com/dotnet/roslyn-analyzers/issues/372)
[CA1007](ca1007-use-generics-where-appropriate.md) | [https://github.com/dotnet/roslyn-analyzers/issues/373](https://github.com/dotnet/roslyn-analyzers/issues/373)
[CA1011](ca1011-consider-passing-base-types-as-parameters.md) | [https://github.com/dotnet/roslyn-analyzers/issues/375](https://github.com/dotnet/roslyn-analyzers/issues/375)
[CA1021](ca1021-avoid-out-parameters.md) | [https://github.com/dotnet/roslyn-analyzers/issues/377](https://github.com/dotnet/roslyn-analyzers/issues/377)
[CA1023](ca1023-indexers-should-not-be-multidimensional.md) | [https://github.com/dotnet/roslyn-analyzers/issues/378](https://github.com/dotnet/roslyn-analyzers/issues/378)
[CA1045](ca1045-do-not-pass-types-by-reference.md) | [https://github.com/dotnet/roslyn-analyzers/issues/391](https://github.com/dotnet/roslyn-analyzers/issues/391)
[CA1046](ca1046-do-not-overload-operator-equals-on-reference-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/392](https://github.com/dotnet/roslyn-analyzers/issues/392)
[CA1047](ca1047-do-not-declare-protected-members-in-sealed-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/393](https://github.com/dotnet/roslyn-analyzers/issues/393)
[CA1048](ca1048-do-not-declare-virtual-members-in-sealed-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/394](https://github.com/dotnet/roslyn-analyzers/issues/394)
[CA1049](ca1049-types-that-own-native-resources-should-be-disposable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/395](https://github.com/dotnet/roslyn-analyzers/issues/395)
[CA1057](ca1057-string-uri-overloads-call-system-uri-overloads.md) | [https://github.com/dotnet/roslyn-analyzers/issues/401](https://github.com/dotnet/roslyn-analyzers/issues/401)
[CA1300](ca1300-specify-messageboxoptions.md) | [https://github.com/dotnet/roslyn-analyzers/issues/408](https://github.com/dotnet/roslyn-analyzers/issues/408)
[CA1301](ca1301-avoid-duplicate-accelerators.md) | [https://github.com/dotnet/roslyn-analyzers/issues/409](https://github.com/dotnet/roslyn-analyzers/issues/409)
[CA1306](ca1306-set-locale-for-data-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/414](https://github.com/dotnet/roslyn-analyzers/issues/414)
[CA1402](ca1402-avoid-overloads-in-com-visible-interfaces.md) | [https://github.com/dotnet/roslyn-analyzers/issues/418](https://github.com/dotnet/roslyn-analyzers/issues/418)
[CA1403](ca1403-auto-layout-types-should-not-be-com-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/419](https://github.com/dotnet/roslyn-analyzers/issues/419)
[CA1404](ca1404-call-getlasterror-immediately-after-p-invoke.md) | [https://github.com/dotnet/roslyn-analyzers/issues/420](https://github.com/dotnet/roslyn-analyzers/issues/420)
[CA1405](ca1405-com-visible-type-base-types-should-be-com-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/421](https://github.com/dotnet/roslyn-analyzers/issues/421)
[CA1407](ca1407-avoid-static-members-in-com-visible-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/423](https://github.com/dotnet/roslyn-analyzers/issues/423)
[CA1408](ca1408-do-not-use-autodual-classinterfacetype.md) | [https://github.com/dotnet/roslyn-analyzers/issues/424](https://github.com/dotnet/roslyn-analyzers/issues/424)
[CA1409](ca1409-com-visible-types-should-be-creatable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/425](https://github.com/dotnet/roslyn-analyzers/issues/425)
[CA1410](ca1410-com-registration-methods-should-be-matched.md) | [https://github.com/dotnet/roslyn-analyzers/issues/426](https://github.com/dotnet/roslyn-analyzers/issues/426)
[CA1411](ca1411-com-registration-methods-should-not-be-visible.md) | [https://github.com/dotnet/roslyn-analyzers/issues/427](https://github.com/dotnet/roslyn-analyzers/issues/427)
[CA1412](ca1412-mark-comsource-interfaces-as-idispatch.md) | [https://github.com/dotnet/roslyn-analyzers/issues/428](https://github.com/dotnet/roslyn-analyzers/issues/428)
[CA1413](ca1413-avoid-non-public-fields-in-com-visible-value-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/429](https://github.com/dotnet/roslyn-analyzers/issues/429)
[CA1414](ca1414-mark-boolean-p-invoke-arguments-with-marshalas.md) | [https://github.com/dotnet/roslyn-analyzers/issues/430](https://github.com/dotnet/roslyn-analyzers/issues/430)
[CA1415](ca1415-declare-p-invokes-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/431](https://github.com/dotnet/roslyn-analyzers/issues/431)
[CA1500](ca1500-variable-names-should-not-match-field-names.md) | [https://github.com/dotnet/roslyn-analyzers/issues/432](https://github.com/dotnet/roslyn-analyzers/issues/432)
[CA1600](ca1600-do-not-use-idle-process-priority.md) | [https://github.com/dotnet/roslyn-analyzers/issues/438](https://github.com/dotnet/roslyn-analyzers/issues/438)
[CA1601](ca1601-do-not-use-timers-that-prevent-power-state-changes.md) | [https://github.com/dotnet/roslyn-analyzers/issues/439](https://github.com/dotnet/roslyn-analyzers/issues/439)
[CA1700](ca1700-do-not-name-enum-values-reserved.md) | [https://github.com/dotnet/roslyn-analyzers/issues/440](https://github.com/dotnet/roslyn-analyzers/issues/440)
[CA1704](ca1704-identifiers-should-be-spelled-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/443](https://github.com/dotnet/roslyn-analyzers/issues/443)
[CA1709](ca1709-identifiers-should-be-cased-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/445](https://github.com/dotnet/roslyn-analyzers/issues/445)
[CA1713](ca1713-events-should-not-have-before-or-after-prefix.md) | [https://github.com/dotnet/roslyn-analyzers/issues/449](https://github.com/dotnet/roslyn-analyzers/issues/449)
[CA1719](ca1719-parameter-names-should-not-match-member-names.md) | [https://github.com/dotnet/roslyn-analyzers/issues/453](https://github.com/dotnet/roslyn-analyzers/issues/453)
[CA1722](ca1722-identifiers-should-not-have-incorrect-prefix.md) | [https://github.com/dotnet/roslyn-analyzers/issues/455](https://github.com/dotnet/roslyn-analyzers/issues/455)
[CA1726](ca1726-use-preferred-terms.md) | [https://github.com/dotnet/roslyn-analyzers/issues/458](https://github.com/dotnet/roslyn-analyzers/issues/458)
[CA1804](ca1804-remove-unused-locals.md) | [https://github.com/dotnet/roslyn-analyzers/issues/461](https://github.com/dotnet/roslyn-analyzers/issues/461)
[CA1811](ca1811-avoid-uncalled-private-code.md) | [https://github.com/dotnet/roslyn-analyzers/issues/464](https://github.com/dotnet/roslyn-analyzers/issues/464)
[CA1900](ca1900-value-type-fields-should-be-portable.md) | [https://github.com/dotnet/roslyn-analyzers/issues/474](https://github.com/dotnet/roslyn-analyzers/issues/474)
[CA2001](ca2001-avoid-calling-problematic-methods.md) | [https://github.com/dotnet/roslyn-analyzers/issues/477](https://github.com/dotnet/roslyn-analyzers/issues/477)
[CA2004](ca2004-remove-calls-to-gc-keepalive.md) | [https://github.com/dotnet/roslyn-analyzers/issues/479](https://github.com/dotnet/roslyn-analyzers/issues/479)
[CA2006](ca2006-use-safehandle-to-encapsulate-native-resources.md) | [https://github.com/dotnet/roslyn-analyzers/issues/480](https://github.com/dotnet/roslyn-analyzers/issues/480)
[CA2109](ca2109-review-visible-event-handlers.md) | [https://github.com/dotnet/roslyn-analyzers/issues/488](https://github.com/dotnet/roslyn-analyzers/issues/488)
[CA2204](ca2204-literals-should-be-spelled-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/529](https://github.com/dotnet/roslyn-analyzers/issues/529)
[CA2205](ca2205-use-managed-equivalents-of-win32-api.md) | [https://github.com/dotnet/roslyn-analyzers/issues/530](https://github.com/dotnet/roslyn-analyzers/issues/530)
[CA2212](ca2212-do-not-mark-serviced-components-with-webmethod.md) | [https://github.com/dotnet/roslyn-analyzers/issues/534](https://github.com/dotnet/roslyn-analyzers/issues/534)
[CA2215](ca2215-dispose-methods-should-call-base-class-dispose.md) | [https://github.com/dotnet/roslyn-analyzers/issues/535](https://github.com/dotnet/roslyn-analyzers/issues/535)
[CA2232](ca2232-mark-windows-forms-entry-points-with-stathread.md) | [https://github.com/dotnet/roslyn-analyzers/issues/545](https://github.com/dotnet/roslyn-analyzers/issues/545)
[CA2236](ca2236-call-base-class-methods-on-iserializable-types.md) | [https://github.com/dotnet/roslyn-analyzers/issues/548](https://github.com/dotnet/roslyn-analyzers/issues/548)
[CA2238](ca2238-implement-serialization-methods-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/549](https://github.com/dotnet/roslyn-analyzers/issues/549)
[CA2239](ca2239-provide-deserialization-methods-for-optional-fields.md) | [https://github.com/dotnet/roslyn-analyzers/issues/550](https://github.com/dotnet/roslyn-analyzers/issues/550)
[CA2240](ca2240-implement-iserializable-correctly.md) | [https://github.com/dotnet/roslyn-analyzers/issues/551](https://github.com/dotnet/roslyn-analyzers/issues/551)

### <a name="deprecated-rules"></a>不推荐使用的规则

以下 FxCop 静态代码分析规则不推荐使用，而不会作为分析器实现。 有关详细信息，您可以搜索按规则 ID (例如， **CA1009**) 上[roslyn 分析器 GitHub 问题页](https://github.com/dotnet/roslyn-analyzers/issues?utf8=%E2%9C%93&q=is:issue+label:FxCop-Port)。

- [CA1009](ca1009-declare-event-handlers-correctly.md)
- [CA1020](ca1020-avoid-namespaces-with-few-types.md)
- [CA1025](ca1025-replace-repetitive-arguments-with-params-array.md)
- [CA1026](ca1026-default-parameters-should-not-be-used.md)
- [CA1035](ca1035-icollection-implementations-have-strongly-typed-members.md)
- [CA1038](ca1038-enumerators-should-be-strongly-typed.md)
- [CA1039](ca1039-lists-are-strongly-typed.md)
- [CA1059](ca1059-members-should-not-expose-certain-concrete-types.md)
- [CA1302](ca1302-do-not-hardcode-locale-specific-strings.md)
- [CA1400](ca1400-p-invoke-entry-points-should-exist.md)
- [CA1406](ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)
- [CA1504](ca1504-review-misleading-field-names.md)
- [CA1701](ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1702](ca1702-compound-words-should-be-cased-correctly.md)
- [CA1703](ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1800](ca1800-do-not-cast-unnecessarily.md)
- [CA1809](ca1809-avoid-excessive-locals.md)
- [CA1901](ca1901-p-invoke-declarations-should-be-portable.md)
- [CA1903](ca1903-use-only-api-from-targeted-framework.md)
- [CA2003](ca2003-do-not-treat-fibers-as-threads.md)
- [CA2102](ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)
- [CA2103](ca2103-review-imperative-security.md)
- [CA2104](ca2104-do-not-declare-read-only-mutable-reference-types.md)
- [CA2105](ca2105-array-fields-should-not-be-read-only.md)
- [CA2106](ca2106-secure-asserts.md)
- [CA2107](ca2107-review-deny-and-permit-only-usage.md)
- [CA2108](ca2108-review-declarative-security-on-value-types.md)
- [CA2111](ca2111-pointers-should-not-be-visible.md)
- [CA2112](ca2112-secured-types-should-not-expose-fields.md)
- [CA2114](ca2114-method-security-should-be-a-superset-of-type.md)
- [CA2115](ca2115-call-gc-keepalive-when-using-native-resources.md)
- [CA2116](ca2116-aptca-methods-should-only-call-aptca-methods.md)
- [CA2117](ca2117-aptca-types-should-only-extend-aptca-base-types.md)
- [CA2118](ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)
- [CA2120](ca2120-secure-serialization-constructors.md)
- [CA2121](ca2121-static-constructors-should-be-private.md)
- [CA2122](ca2122-do-not-indirectly-expose-methods-with-link-demands.md)
- [CA2123](ca2123-override-link-demands-should-be-identical-to-base.md)
- [CA2124](ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)
- [CA2126](ca2126-type-link-demands-require-inheritance-demands.md)
- [CA2130](ca2130-security-critical-constants-should-be-transparent.md)
- [CA2131](ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)
- [CA2132](ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)
- [CA2133](ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)
- [CA2134](ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)
- [CA2135](ca2135-level-2-assemblies-should-not-contain-linkdemands.md)
- [CA2136](ca2136-members-should-not-have-conflicting-transparency-annotations.md)
- [CA2137](ca2137-transparent-methods-must-contain-only-verifiable-il.md)
- [CA2138](ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)
- [CA2139](ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute.md)
- [CA2140](ca2140-transparent-code-must-not-reference-security-critical-items.md)
- [CA2141](ca2141-transparent-methods-must-not-satisfy-linkdemands.md)
- [CA2142](ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)
- [CA2143](ca2143-transparent-methods-should-not-use-security-demands.md)
- [CA2144](ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)
- [CA2145](ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)
- [CA2146](ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)
- [CA2147](ca2147-transparent-methods-may-not-use-security-asserts.md)
- [CA2149](ca2149-transparent-methods-must-not-call-into-native-code.md)
- [CA2151](ca2151-fields-with-critical-types-should-be-security-critical.md)
- [CA2202](ca2202-do-not-dispose-objects-multiple-times.md)
- [CA2210](ca2210-assemblies-should-have-valid-strong-names.md)
- [CA2220](ca2220-finalizers-should-call-base-class-finalizer.md)
- [CA2221](ca2221-finalizers-should-be-protected.md)
- [CA2222](ca2222-do-not-decrease-inherited-member-visibility.md) ([理由](https://github.com/dotnet/roslyn-analyzers/issues/1378))
- [CA2223](ca2223-members-should-differ-by-more-than-return-type.md)
- [CA2228](ca2228-do-not-ship-unreleased-resource-formats.md)
- [CA2230](ca2230-use-params-for-variable-arguments.md)
- [CA2233](ca2233-operations-should-not-overflow.md)
- [CA5122](ca5122-p-invoke-declarations-should-not-be-safe-critical.md)

## <a name="see-also"></a>请参阅

- [Microsoft.CodeAnalysis.FxCopAnalyzers rules](https://github.com/dotnet/roslyn-analyzers/blob/master/src/Microsoft.CodeAnalysis.FxCopAnalyzers/Microsoft.CodeAnalysis.FxCopAnalyzers.md)