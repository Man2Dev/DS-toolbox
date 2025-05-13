**External Module Integration**

## Attribution

This repository (`DS-toolbox`) integrates the [Data Science Toolkit](https://github.com/pmaji/data-science-toolkit) as an external module.

The **data-science-toolkit** is maintained by [pmaji](https://github.com/pmaji) and provides useful tools for data science workflows. For more details and documentation, visit the [Data Science Toolkit repository](https://github.com/pmaji/data-science-toolkit).

### Working with Submodules

This repository uses **data-science-toolkit** as a Git submodule. After cloning this repository, initialize and update the submodule with:

```bash
git clone https://github.com/yourusername/DS-toolbox.git
cd DS-toolbox
git submodule update --init --recursive
```

To update the submodule to the latest upstream changes in the future, run:

```bash
git submodule update --remote --merge
```

---

*Now you have the `data-science-toolkit` available under the `external/data-science-toolkit/` directory. You can import and use its modules directly in your notebooks or scripts.*
