# level: 11
username: bandit11

## notes:
* decode rot13 substitution cypher
* rot13 replaces each character in a string with the 13th letter after it in the alphabet
* using rot13 again on the cypher decodes it as 13x2=26
* used command tr
* **solution:** 
  ```bash
  cat  data.txt
  tr 'A-Za-z' 'N-ZA-Mn-za-m' <<< 'Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4'
  ```

## approach:
* extract the text from the data file and try to implement rot13 cypher again to the text to decode it
