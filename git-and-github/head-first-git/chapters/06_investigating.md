# Investigating Your Git Repository

Git Log

vi använder git log för att skriva ut vår commit history

Här kan vi använda flags såsom —graph —oneline —decorate —parents

- **`-graph`**: This flag adds a visual representation of the branch structure in the log output. It uses ASCII characters to draw a graph showing the branch and merge history.
- **`-oneline`**: This flag condenses each commit to a single line. It shows the commit hash and the commit message, making the log easier to read and scan quickly.
- **`-decorate`**: This flag adds information about branches, tags, and other references to the commit messages in the log output. It helps to see where the current commit is in relation to these references.
- **`-parents`**: This flag shows the parent commit hashes for each commit. It is useful for understanding the ancestry and merge history of the commits.
- **`—all`** : Detta får ut loggen ifrån varje branch och tags.

Här är en git log —all —parents

Här kan vi se att branch different-base och spicy-version båda började ifrån master branchens senaste commit.

Parent commit id är det andra commit id’t vi ser:

![Untitled](../img/investigating-your-git-repo/Untitled.png)
