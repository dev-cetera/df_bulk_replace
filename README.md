[![pub](https://img.shields.io/pub/v/df_bulk_replace.svg)](https://pub.dev/packages/df_bulk_replace)
[![tag](https://img.shields.io/badge/Tag-v0.3.0-purple?logo=github)](https://github.com/dev-cetera/df_bulk_replace/tree/v0.3.0)
[![instagram](https://img.shields.io/badge/Instagram-E4405F?logo=instagram&logoColor=white)](https://www.instagram.com/dev_cetera/)
[![license](https://img.shields.io/badge/License-MIT-blue.svg)](https://raw.githubusercontent.com/dev-cetera/df_bulk_replace/main/LICENSE)

---

<!-- BEGIN _README_CONTENT -->

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

## Examples

```sh
# Basic replacment.
bulkreplace --input test --replace "foo" --with "bar"
bulkreplace -i test -r "bar" -w "foo"
bulkreplace -i test -r "replace_me" -w "vervang_my"
bulkreplace -i test -r "vervang_my" -w "replace_me" # change back
bulkreplace -i test -r "replace_me" -w "vervang_my" && bulkreplace -i test -r "vervang_my" -w "replace_me"

# Using handlebars.
bulkreplace -i test -r "replace_me_(\\w)_(\\w)_(\\w)" -w "replace_me_{{2}}_{{1}}_{{0}}" --no-file-names --no-folder-names

# Whitelisting or blacklisting files.
bulkreplace -i test -r "foo" -w "bar" --blacklisted-files "blacklist_me_1.txt, blacklist_me_2.txt"
bulkreplace -i test -r "foo" -w "bar" --whitelisted-files "whitelist_me_1.txt, whitelist_me_2.txt"

# Whitelisting or blacklisting folders.
bulkreplace -i test -r "foo" -w "bar" --blacklisted-folders "_blacklist_me" -v
bulkreplace -i test -r "foo" -w "bar" --whitelisted-folders "_whitelist_me" -v

# For those familiar with RegExp, you can use regular expressions and capture groups.
bulkreplace --i . --replace "my_project_template(.*)" --with "hello_world{{1}}"
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

<!-- END _README_CONTENT -->

---

🔍 For more information, refer to the [API reference](https://pub.dev/documentation/df_bulk_replace/).

---

## 💬 Contributing and Discussions

This is an open-source project, and we warmly welcome contributions from everyone, regardless of experience level. Whether you're a seasoned developer or just starting out, contributing to this project is a fantastic way to learn, share your knowledge, and make a meaningful impact on the community.

### ☝️ Ways you can contribute

- **Raise a ticket:** Open an issue on the [GitHub repository](https://github.com/dev-cetera/df_bulk_replace/issues) for questions, bugs and feature requests.
- **Get in touch:** Email [hello@robertsolves.com.au](mailto:hello@robertsolves.com.au) if you would like to contribute or collaborate.
- **Share your ideas:** Every perspective matters, and your ideas can spark innovation.
- **Help others:** Engage with other users by offering advice, solutions, or troubleshooting assistance.
- **Report bugs:** Help us identify and fix issues to make the project more robust.
- **Suggest improvements or new features:** Your ideas can help shape the future of the project.
- **Help clarify documentation:** Good documentation is key to accessibility. You can make it easier for others to get started by improving or expanding our documentation.
- **Write articles:** Share your knowledge by writing tutorials, guides, or blog posts about your experiences with the project. It's a great way to contribute and help others learn.

No matter how you choose to contribute, your involvement is greatly appreciated and valued!

## 👤 Author & Contact

- Website: [robertsolves.com.au](https://robertsolves.com.au)
- Organization: [dev-cetera.com](https://dev-cetera.com)
- Email: [robert@dev-cetera.com](mailto:robert@dev-cetera.com) or [hello@robertsolves.com.au](mailto:hello@robertsolves.com.au)

## LICENSE

This project is released under the [MIT License](https://raw.githubusercontent.com/dev-cetera/df_bulk_replace/main/LICENSE). See [LICENSE](https://raw.githubusercontent.com/dev-cetera/df_bulk_replace/main/LICENSE) for more information.
