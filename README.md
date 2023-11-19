# arabia

`Chiffre` gasigasy na koa hoe `Système de chiffrement par substitution` tsotra kely fampiasan'ny sasany eto Dago indraindray.

Mampahatsiahy ny fahazazana ary indrindra indrindra indrindra ny [Code César](https://fr.wikipedia.org/wiki/Chiffrement_par_d%C3%A9calage) izay `abidy` hianaran'ny rehetra mandalina *cryptographie*/*cryptanalyse* eo ampiandohana.


```rust
pub fn arb(text: &str) -> String {
    let input  = "BDFGHJKLMNPRSTVZbdfghjklmnprstvz";
    let output = "ZVTSRPNMLKJHGFDBzvtsrpnmlkjhgfdb";

    text.chars()
        .map(|c| match input.find(c) {
            Some(i) => output.chars().nth(i).unwrap(),
            None => c,
        })
        .collect()
}

fn main() {
    let str_in: &str = "LIAHARAZA AKAHEO HEREFHA FHAFHY KY FAOKA E";

    println!("Teny adika  <<<: {}", str_in);
    println!(">>> Dika mazava: {} >>>", arb(str_in));
}
```


```
Teny adika  <<<: LIAHARAZA AKAHEO HEREFHA FHAFHY KY FAOKA E
>>> Dika mazava: MIARAHABA ANAREO REHETRA TRATRY NY TAONA E >>>
```
