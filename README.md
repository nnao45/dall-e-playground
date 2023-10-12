# dall-e-playground
```#+BEGIN_QUERY
{:title [:h2 "DONE"]
 :query [:find (pull ?b [*])
  :in $ ?query-page
  :where
   [?b :block/refs ?journal]
   [?b :block/marker "DONE"]
   [?b :block/properties ?properties]
   [?journal :block/name ?query-page]
 ]
 :inputs [:query-page]
 :table-view? false;
 :breadcrumb-show? false ;
 :collapsed? false;
  :result-transform (fn [result] (
                                     sort-by (fn [r] (get-in r [:block/properties :completed]))
                               result))

}
#+END_QUERY```
