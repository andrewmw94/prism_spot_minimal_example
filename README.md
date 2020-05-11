# prism_spot_minimal_example

To run PRISM:
```prism lr5_ltl.nm ltl5.props```


To run SPOT:
```export LTL2DSTAR=/home/awells/Development/ltl2a/ltl2dstar-0.5.4/build/ltl2dstar```
```prism lr5_ltl.nm ltl5.props -ltl2datool ~/Development/prism/prism/etc/scripts/hoa/hoa-ltl2dstar-with-ltl2tgba-for-prism -ltl2dasyntax lbt```


You can also export the automata from each for comparison:
(Change the paths to match your installations.)
```prism lr5_ltl.nm ltl5.props -exportpropaut prism_exported_automata.hoa```
```prism lr5_ltl.nm ltl5.props -ltl2datool ~/Development/prism/prism/etc/scripts/hoa/hoa-ltl2dstar-with-ltl2tgba-for-prism -ltl2dasyntax lbt -exportpropaut spot_exported_automata.hoa```


hoa_test_prism_exported just copies the automaton. Copying gives the same results, so I believe the issue is due to the automata themselves and not e.g., some re-used computation within PRISM from building the automaton.

To run this:
Change the path in hoa_test_prism_exported to match the automata you want to import (prism_exported_automata.hoa or spot_exported_automata.hoa).
```prism lr5_ltl.nm ltl5.props -ltl2datool ./hoa_test_prism_exported -ltl2dasyntax spot```