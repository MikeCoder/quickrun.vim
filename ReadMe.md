quickrun.vim
---

![GitHub release (latest SemVer including pre-releases)](https://img.shields.io/github/v/release/D0n9x1n/quickrun.vim?include_prereleases)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat)](https://mit-license.org/)

Yet, just another quickrun plugin for vim.

### Installation
Take Vundle as an example:

+ Add `Plugin 'MikeCoder/quickrun.vim'` to your vimrc file.
+ Then use `Vundle Install` to install this plugin.


### Config
In this plugin, the default run config has been set as following:
```
let g:quickrun_known_file_types = {
        \"cpp": ["!g++ %", "./a.out"],
        \"c": ["!gcc %", "./a.out"],
        \"php": ["!php %"],
        \"vim": ["source %"],
        \"py": ["!python %"],
    \}
```

These configuration means, when you edit a file with ".cpp". You will use `!g++ % && ./a.out` to run this file.

So, you can add your customize configuration here. If you want to use `:go test` command when you edit go files. You can add your config like this:

```
let g:quickrun_known_file_types = {
        \"cpp": ["!g++ %", "./a.out"],
        \"c": ["!gcc %", "./a.out"],
        \"php": ["!php %"],
        \"vim": ["source %"],
        \"py": ["!python %"],
        \"go": ["!go test"],
    \}
```

Here we use `%` to represent the file you currently edit.

This configuration you can write in your **vimrc file**.

### Config with config file
You can add `.quickrun` file into your project folder and write your shell there. The plugin will find that file and run commands there.

For example, you can write the following commands in `.quickrun`

```
hexo clean && hexo generate && hexo server
```

Then, run `QuickRun`, you will run the command in your vim.

### Usage
1. Auto detect the filetype.
> + When you editing your file, You can run `:QuickRun` to run your current file.
> + If you are editting *main.c* file, the command will be `:!gcc main.c && ./a.out`.

2. Run with spec filetype.
> + When you editing your file, you can run `:QuickRunWithType go` to run your current file.
> + If you are editting *main.md*, the command will be `:!go test` to test the whole go project.

3. You can bind your key with `nnoremap <F5> :QuickRun<cr>` to enjoy the plugin.

### License
See [@LICENSE](./LICENSE)


### TODO
See [@TODO.md](./TODO.md)
