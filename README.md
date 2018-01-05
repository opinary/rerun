This is modified version of https://github.com/skelterjohn/rerun project.

In addition to base functionality, google cloud application YAML file can be specified. When provided, environment variables are load from it.

Example:

    rerun \
        -conf github.com/opinary/app/foobar/staging.yaml \
        github.com/opinary/app/foobar

`-conf` flag MUST BE provided BEFORE project path to be used by `rerun` and not passed through as project's execution parameter.

---

Use like ```rerun github.com/skelterjohn/go.uik/uiktest```

Usage: ```rerun [--test] [--build] [--race] [--no-run] <import path> [arg]*```

For any go executable in a normal GOPATH workspace, rerun will watch its source,
rebuild, retest, and rerun. As long as ```go install <import path>``` works,
rerun will be able to find it.

Along with the target's source, rerun also watches the source of all
the target's non-GOROOT dependencies.

When using flag `--test`, rerun executes `go test`. If tests fail, rerun will not continue to build and/or run the program.

Flag `--build` makes rerun execute `go build` in the local folder, creating an executable.

Flag `--no-run` omits actually running the program. This is useful if you only wish to test and/or build.

Flag `--race` will test/build/run the program with race detection enabled.
