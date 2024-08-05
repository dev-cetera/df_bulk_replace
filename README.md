# DF Bulk Replace

Dart & Flutter Packages by DevCetra.com & contributors.

[![Pub Package](https://img.shields.io/pub/v/df_bulk_replace.svg)](https://pub.dev/packages/df_bulk_replace)
[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg)](https://raw.githubusercontent.com/robmllze/df_bulk_replace/main/LICENSE)

---

## Summary

A command-line tool to perform bulk replacement of file names, folder names, and file contents within a specified directory.

## How It Works

1.  The script scans the specified directory recursively and finds all files and folders.
2.  It replaces the occurrences of the `replace` pattern with the `with` pattern in the file contents, file names, and folder names.
3.  The script supports using capture groups in the replacement pattern using double curly braces `{{}}`.

## Installing

```sh
dart pub global activate df_bulk_replace
```

## Uninstalling

```sh
dart pub global deactivate df_bulk_replace
```

## Usage Examples

```sh
# Basic replacment.
bulk_replace --input test --replace "foo" --with "bar"
bulk_replace -i test -r "bar" -w "foo"
bulk_replace -i test -r "replace_me" -w "vervang_my"
bulk_replace -i test -r "vervang_my" -w "replace_me" # change back
bulk_replace -i test -r "replace_me" -w "vervang_my" && bulk_replace -i test -r "vervang_my" -w "replace_me"

# Using handlebars.
bulk_replace -i test -r "replace_me_(\\w)_(\\w)_(\\w)" -w "replace_me_{{2}}_{{1}}_{{0}}" --no-file-names --no-folder-names

# Whitelisting or blacklisting files.
bulk_replace -i test -r "foo" -w "bar" --blacklisted-files "blacklist_me_1.txt, blacklist_me_2.txt"
bulk_replace -i test -r "foo" -w "bar" --whitelisted-files "whitelist_me_1.txt, whitelist_me_2.txt"

# Whitelisting or blacklisting folders.
bulk_replace -i test -r "foo" -w "bar" --blacklisted-folders "_blacklist_me" -v
bulk_replace -i test -r "foo" -w "bar" --whitelisted-folders "_whitelist_me" -v

# For those familiar with RegExp, you can use regular expressions and capture groups.
bulk_replace --i . --replace "my_project_template(.*)" --with "hello_world{{1}}"
```

## Arguments

Prints help: **-h** or **--help**

Specifies the directory to search in: **-i** or **--input**

Specifies the regex pattern to replace: **-r** or **--replace**

Specifies the replacement string: **-w** or **--with**

Enables verbose output: **-v** or **--verbose**

Runs the program in dry-run mode (no files will be renamed): **--dry-run**

Specifies whether to replace file names or not. Default is true: **-f** or **--file-names**

Specifies whether to replace folder names or not. Default is true: **-d** or **--folder-names**

Specifies whether to replace file content or not. Default is true: **-c** or **--content**

Specifies whether to replace content in binary files or not. Default is false: **-b** or **--binary-content**

Include file name patterns to whitelist. Separate multiple patterns with commas: **--whitelisted-files**

Include file name patterns to blacklist. Separate multiple patterns with commas: **--blacklisted-files**

Specifies whether to add the default file whitelist or not. Default is true: **--default-whitelisted-files**

Specifies whether to add the default file blacklist or not. Default is true: **--default-blacklisted-files**

Include folder name patterns to whitelist. Separate multiple patterns with commas: **--whitelisted-folders**

Include folder name patterns to blacklist. Separate multiple patterns with commas: **--blacklisted-folders**

---

## Contributing and Discussions

This is an open-source project, and contributions are welcome from everyone, regardless of experience level. Contributing to projects is a great way to learn, share knowledge, and showcase your skills to the community. Join the discussions to ask questions, report bugs, suggest features, share ideas, or find out how you can contribute.

### Join GitHub Discussions:

💬 https://github.com/robmllze/df_bulk_replace/discussions/

### Join Reddit Discussions:

💬 https://www.reddit.com/r/df_bulk_replace/

### Chief Maintainer:

📧 Email _Robert Mollentze_ at robmllze@gmail.com

---

## License

This project is released under the MIT License. See [LICENSE](https://raw.githubusercontent.com/robmllze/df_bulk_replace/main/LICENSE) for more information.
