A string containing a translation source message.

包含翻译源消息的字符串。

I.E. the message that indicates what will be translated from.

IE 表明将要翻译的内容的消息。

Uses `{$placeholder-name}` to indicate a placeholder.

使用 `{$placeholder-name}` 来表示占位符。

A string containing a translation target message.

包含翻译目标消息的字符串。

I.E. the message that indicates what will be translated to.

IE 表明将要翻译为内容的消息。

A string that uniquely identifies a message, to be used for matching translations.

唯一标识消息的字符串，用于匹配翻译。

Declares a copy of the `AbsoluteFsPath` branded type in `@angular/compiler-cli` to avoid an
import into `@angular/compiler-cli`. The compiler-cli's declaration files are not necessarily
compatible with web environments that use `@angular/localize`, and would inadvertently include
`typescript` declaration files in any compilation unit that uses `@angular/localize` \(which
increases parsing time and memory usage during builds\) using a default import that only
type-checks when `allowSyntheticDefaultImports` is enabled.

在 `@angular/compiler-cli` 中声明 `AbsoluteFsPath` 品牌类型的副本，以避免导入到
`@angular/compiler-cli`。compiler-cli 的声明文件不一定与使用 `@angular/localize`
`@angular/localize` `typescript` Web 环境兼容，并且会使用默认导入，仅在启用
`allowSyntheticDefaultImports` 时才进行类型检查。

The location of the message in the source file.

消息在源文件中的位置。

The `line` and `column` values for the `start` and `end` properties are zero-based.

`start` 和 `end` 属性的 `line` 值和 `column` 值是从零开始的。

Additional information that can be associated with a message.

可以与消息关联的附加信息。

A human readable rendering of the message

消息的人类可读渲染

Legacy message ids, if provided.

旧版消息 ID（如果提供）。

In legacy message formats the message id can only be computed directly from the original
template source.

在旧版消息格式中，消息 id 只能直接从原始模板源计算。

Since this information is not available in `$localize` calls, the legacy message ids may be
attached by the compiler to the `$localize` metablock so it can be used if needed at the point
of translation if the translations are encoded using the legacy message id.

由于此信息在 `$localize` 调用中不可用，因此编译器可以将旧版消息 ID 附加到 `$localize`
元块，因此如果翻译是使用旧版消息 ID 编码的，则可以在翻译时使用它。

The id of the `message` if a custom one was specified explicitly.

如果显式指定了自定义消息，则为 `message` 的 id。

This id overrides any computed or legacy ids.

此 id 会覆盖任何计算得出的 id 或旧版 id。

The meaning of the `message`, used to distinguish identical `messageString`s.

`message` 的含义，用于区分相同的 `messageString`。

The description of the `message`, used to aid translation.

`message` 的描述，用于帮助翻译。

The location of the message in the source.

消息在源中的位置。

Information parsed from a `$localize` tagged string that is used to translate it.

从用于翻译它的 `$localize` 标记字符串解析的信息。

For example:

例如：

May be parsed into:

可以解析为：

The key used to look up the appropriate translation target.

用于查找适当的翻译目标的键。

A mapping of placeholder names to substitution values.

占位符名称到替换值的映射。

An optional mapping of placeholder names to associated MessageIds.
This can be used to match ICU placeholders to the message that contains the ICU.

占位符名称到关联的 MessageIds 的可选映射。这可用于将 ICU 占位符与包含 ICU 的消息匹配。

An optional mapping of placeholder names to source locations

占位符名称到源位置的可选映射

The static parts of the message.

消息的静态部分。

An optional mapping of message parts to source locations

消息部分到源位置的可选映射

The names of the placeholders that will be replaced with substitutions.

将被替换的占位符的名称。

Parse a `$localize` tagged string into a structure that can be used for translation or
extraction.

将 `$localize` 标记字符串解析为可用于翻译或提取的结构。

See `ParsedMessage` for an example.

有关示例，请参阅 `ParsedMessage`。

The cooked version of the message part to parse.

要解析的消息部分的成熟版本。

The raw version of the message part to parse.

要解析的消息部分的原始版本。

A object containing any metadata that was parsed from the message part.

包含从消息部分解析的任何元数据的对象。

Parse the given message part \(`cooked` + `raw`\) to extract the message metadata from the text.

解析给定的消息部分（`cooked` + `raw`）以从文本中提取消息元数据。

If the message part has a metadata block this function will extract the `meaning`,
`description`, `customId` and `legacyId` \(if provided\) from the block. These metadata properties
are serialized in the string delimited by `|`, `@@` and `␟` respectively.

如果消息部分有一个元数据块，此函数将从块中提取 `meaning`、`description`、`customId` 和
`legacyId`（如果提供）。这些元数据属性在由 `|` 分隔的字符串中序列化、 `@@` 和 `␟`。

\(Note that `␟` is the `LEGACY_ID_INDICATOR` - see `constants.ts`.\)

（请注意，`␟` 是 `LEGACY_ID_INDICATOR` - 请参阅 `constants.ts`。）

A object containing the metadata \(`placeholderName` and `associatedMessageId`\) of the
    preceding placeholder, along with the static text that follows.

包含前面占位符的元数据（`placeholderName` 和 `associatedMesssageId`）以及后面的静态文本的对象。

Parse the given message part \(`cooked` + `raw`\) to extract any placeholder metadata from the
text.

解析给定的消息部分（`cooked` + `raw`）以从文本中提取任何占位符元数据。

If the message part has a metadata block this function will extract the `placeholderName` and
`associatedMessageId` \(if provided\) from the block.

如果消息部分有一个元数据块，则此函数将从块中提取 `placeholderName` 和 `associatedMessageId`
（如果提供）。

These metadata properties are serialized in the string delimited by `@@`.

这些元数据属性在由 `@@` 分隔的字符串中序列化。

An object containing the `text` of the message part and the text of the `block`, if it
exists.

一个对象，包含消息部分的 `text` 和 `block` 的文本（如果存在）。

an error if the `block` is unterminated

如果 `block` 未终止，则出现错误

Split a message part \(`cooked` + `raw`\) into an optional delimited "block" off the front and the
rest of the text of the message part.

将消息部分（`cooked` + `raw`）拆分为前面的可选分隔“块”和消息部分的其余文本。

Blocks appear at the start of message parts. They are delimited by a colon `:` character at the
start and end of the block.

块出现在消息部分的开头。它们由块开头和结尾的冒号 `:` 字符分隔。

If the block is in the first message part then it will be metadata about the whole message:
meaning, description, id.  Otherwise it will be metadata about the immediately preceding
substitution: placeholder name.

如果块在第一个消息部分中，那么它将是有关整个消息的元数据：含义、描述、ID。否则，它将是有关前一个替换:
占位符名称的元数据。

Since blocks are optional, it is possible that the content of a message block actually starts
with a block marker. In this case the marker must be escaped `\:`.

由于块是可选的，因此消息块的内容可能实际上以块标记开头。在这种情况下，标记必须进行转译 `\:`。

The cooked string \(where escaped chars have been processed\)

煮熟的字符串（已处理转义字符的地方）

The raw string \(where escape sequences are still in place\)

原始字符串（转义序列仍然存在）

the index of the end of block marker

块标记结尾的索引

an error if the block is unterminated

如果块未终止，则出现错误

Find the end of a "marked block" indicated by the first non-escaped colon.

查找第一个非转义冒号表示的“标记块”的结尾。