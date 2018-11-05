# SVN

[Subversion Book](http://svnbook.red-bean.com/)

## usage

    svn <subcommand> [options] [args]

## common parameters

    -R  // recursive
    --depth infinity

## bunch of examples

    svn move <old path> <new path>  // intuition can be used :)

    svn add <path to file or folder>

    svn cleanup <path> --remove-unversioned --remove-ignored  // requires version 1.9

    svn revert <path> --depth infinity

    svn update <path>

    svn commit <path> --depth infinity --message <message>