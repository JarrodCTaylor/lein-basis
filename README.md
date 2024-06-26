# lein-basis

Use the [add-lib](https://clojure.github.io/clojure/branch-master/clojure.repl-api.html#clojure.repl.deps/add-lib) function in your repl from within a lein project.

# Installation as a Tool

```sh
clj -Ttools install-latest :lib io.github.JarrodCTaylor/lein-basis :as lein-basis
```

# Invoking the tool from a REPL

```clojure
(clojure.tools.deps.interop/invoke-tool {:tool-name "lein-basis" :fn 'lein-basis.core/bootstrap})
```

Now that the bootstrap function has been successfully run. You can proceed to use `add-lib` function as you would in a deps.edn base project. 

For example:
```clojure
(add-lib 'org.clojure/data.json {:mvn/version "2.4.0"})
(require '[clojure.data.json :as json])
(json/read-str "{\"a\":1,\"b\":2}" :key-fn keyword)
```