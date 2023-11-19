# arabia

`Chiffre` gasigasy na koa hoe `Système de chiffrement par substitution` tsotra kely sady fampiasan'ny sasany eto Dago indraindray.

Mampahatsiahy ny fahazazana ary indrindra indrindra ny [Code César](https://fr.wikipedia.org/wiki/Chiffrement_par_d%C3%A9calage) izay `fianarana mamindra` ho an'ireo rehetra mandalina *cryptographie*/*cryptanalyse* eo ampiandohana.

Nitsidika an'i **Serasera Malagasy** dia sendra azy, tsy naharitra ka niakatra ny aingampanahy... 😆😆😆

<p align="center"><img src="screenshot.png"></p>

Miala any ary ny code...

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
    println!(">>> Dika mazava: {}", arb(str_in));
}
```

Raha hanadrana azy dia ampidiro hoe `cargo run` dia tsindrio `return`.

```
Teny adika  <<<: LIAHARAZA AKAHEO HEREFHA FHAFHY KY FAOKA E
>>> Dika mazava: MIARAHABA ANAREO REHETRA TRATRY NY TAONA E
```
Marihana fa sady fanaovana _encodage_ no ampiasana koa amin'ny _décodage_ `pub fn arb(text: &str) -> String`. Pimaso ho an'ireo namana rehetra mankafy Marika: Involution, na Fonction involutive no resaka izany 👀
