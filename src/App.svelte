<script lang="ts">
    import FlashCard from "./lib/FlashCard.svelte";

    // Define flash cards data structure
    const flashCards = [
        // I
        { id: 1, question: "αγγούρι, το", answer: "de komkommer" },
        { id: 2, question: "αεροδρόμιο, το", answer: "het vliegveld" },
        { id: 3, question: "αεροπλάνο, το", answer: "het vliegtuig" },
        { id: 4, question: "βιβλίο, το", answer: "het boek" },
        { id: 5, question: "γεια σας (formeel)", answer: "hallo" },
        { id: 6, question: "γεια σου (informeel)", answer: "hallo" },
        { id: 7, question: "γράμμα, το", answer: "de brief" },
        { id: 8, question: "δρόμος, ο", answer: "de weg" },
        { id: 9, question: "ευχαριστώ", answer: "bedankt" },
        { id: 10, question: "κόκα κόλα, η", answer: "de cola" },
        { id: 11, question: "καλημέρα", answer: "goedemorgen, goedendag" },
        { id: 12, question: "καληνύχτα (afscheid)", answer: "goedenacht" },
        { id: 13, question: "καλησπέρα", answer: "goedenavond" },
        { id: 14, question: "κάνω", answer: "maken, doen" },
        { id: 15, question: "καφές, ο", answer: "de koffie" },
        { id: 16, question: "κρασί, το", answer: "de wijn" },
        { id: 17, question: "λεμονάδα, η", answer: "citroenlimonade" },
        { id: 18, question: "λεμόνι, το", answer: "de citroen" },
        { id: 19, question: "λίγο", answer: "een beetje, weinig" },
        { id: 20, question: "λογαριασμός, ο", answer: "de rekening" },
        { id: 21, question: "λουλούδι, το", answer: "de bloem" },
        { id: 22, question: "μαμά, η", answer: "mama" },
        { id: 23, question: "μέρα, η", answer: "de dag" },
        { id: 24, question: "μουσακάς, ο", answer: "mousaka" },
        { id: 25, question: "μπαμπάς, ο", answer: "papa" },
        { id: 26, question: "μπαρ", answer: "de bar" },
        { id: 27, question: "μπύρα, η", answer: "het biertje" },
        { id: 28, question: "ναι", answer: "ja" },
        { id: 29, question: "νερό, το", answer: "het water" },
        { id: 30, question: "ντομάτα, η", answer: "de tomaat" },
        { id: 31, question: "νύχτα, η", answer: "de nacht" },
        { id: 32, question: "ομπρέλα, η", answer: "paraplu, parasol" },
        { id: 33, question: "ορίστε (aanbieden)", answer: "alstublieft" },
        { id: 34, question: "ούζο, το", answer: "de ouzo" },
        { id: 35, question: "όχι", answer: "nee" },
        { id: 36, question: "παρακαλώ", answer: "alstublieft, geen dank" },
        { id: 37, question: "παιδί, το", answer: "het kind" },
        { id: 38, question: "πίτσα, η", answer: "de pizza" },
        { id: 39, question: "πολύ", answer: "veel, zeer" },
        { id: 40, question: "πορτοκαλάδα, η", answer: "sinaasappelsap" },
        { id: 41, question: "πορτοκάλι, το", answer: "de sinaasappel" },
        { id: 42, question: "πρόβλημα, το", answer: "het probleem" },
        { id: 43, question: "ρετσίνα, η", answer: "de harswijn" },
        { id: 44, question: "σαλάτα, η", answer: "de salade" },
        { id: 45, question: "σινεμά, το", answer: "de bioscoop" },
        { id: 46, question: "σοκολάτα, η", answer: "de chocola" },
        { id: 47, question: "σουβλάκι, το", answer: "souvlaki " },
        { id: 48, question: "σπίτι, το", answer: "het huis" },
        { id: 49, question: "ταβέρνα, η", answer: "de taverne" },
        { id: 50, question: "ταξί, το", answer: "de taxi" },
        { id: 51, question: "τζατζίκι, το", answer: "tzatziki" },
        { id: 52, question: "τουαλέττα, η", answer: "het toilet" },
        { id: 53, question: "τσάι, το", answer: "de thee" },
        { id: 54, question: "φέτα, η", answer: "geitenkaas, schapenkaas" },
        { id: 55, question: "φιλμ, το", answer: "de film" },
        { id: 56, question: "ψωμί, το", answer: "het brood" },
        { id: 57, question: "Γεια μας!", answer: "Proost." },
        { id: 58, question: "Καλή όρεξη!", answer: "Eet smakelijk!" },

        //// II
        //{ id: 59, question: "Αθήνα, η", answer: "Athene" },
        //{ id: 60, question: "αλάτι, το", answer: "het zout" },
        //{ id: 61, question: "άνοιξη, η", answer: "de lente" },
        //{ id: 62, question: "άντρας, ο", answer: "de man" },
        //{ id: 63, question: "αντίο", answer: "vaarwel, adieu, tot ziens" },
        //{ id: 64, question: "από", answer: "van, vanaf, vanuit, uit, vandaan" },
        //{ id: 65, question: "ασπιρίνη, η", answer: "de aspirine" },
        //{ id: 66, question: "αύριο", answer: "morgen" },
        //{ id: 67, question: "αυτοκίνητο, το", answer: "de auto" },
        //{ id: 68, question: "βιβλιοθήκη, η", answer: "de bibliotheek, boekenkast" },
        //{ id: 69, question: "βούτυρο, το", answer: "de boter" },
        //{ id: 70, question: "γάλα, το", answer: "de melk" },
        //{ id: 71, question: "για", answer: "voor, over" },
        //{ id: 72, question: "γιαούρτι, το", answer: "de yoghurt" },
        //{ id: 73, question: "δεν", answer: "niet, geen" },
        //{ id: 74, question: "εβδομάδα, η", answer: "de week" },
        //{ id: 75, question: "εγώ", answer: "ik" },
        //{ id: 76, question: "εδώ", answer: "hier" },
        //{ id: 77, question: "είμαι", answer: "ik ben, zijn" },
        //{ id: 78, question: "εκεί", answer: "daar" },
        //{ id: 79, question: "έλα", answer: "kom" },
        //{ id: 80, question: "ένας/ μία/ ένα", answer: "één, een" },
        //{ id: 81, question: "εσύ", answer: "jij" },
        //{ id: 82, question: "έτοιμος", answer: "klaar, gereed" },
        //{ id: 83, question: "έτσι", answer: "zo/ zomaar" },
        //{ id: 84, question: "έχω", answer: "ik heb, hebben" },
        //{ id: 85, question: "γάτα, η", answer: "de poes" },
        //{ id: 86, question: "γρήγορα", answer: "snel, vlug" },
        //{ id: 87, question: "δώρο, το", answer: "het geschenk" },
        //{ id: 88, question: "ζάχαρη, η", answer: "de suiker" },
        //{ id: 89, question: "θάλασσα, η", answer: "de zee" },
        //{ id: 90, question: "θαύμα, το", answer: "het wonder" },
        //{ id: 91, question: "θέλω", answer: "ik wil, willen" },
        //{ id: 92, question: "Θεσσαλονίκη, η", answer: "Thessaloniki" },
        //{ id: 93, question: "ιστορία, η", answer: "geschiedenis, verhaal" },
        //{ id: 94, question: "και", answer: "en, ook" },
        //{ id: 95, question: "καιρός, ο", answer: "het weer/ de tijd" },
        //{ id: 96, question: "κακός", answer: "slecht, kwaad, verkeerd, boosaardig" },
        //{ id: 97, question: "καλοκαίρι, το", answer: "de zomer" },
        //{ id: 98, question: "καλός", answer: "goed, mooi, aardig, fijn, fatsoenlijk, net" },
        //{ id: 99, question: "κάνω βόλτα", answer: "een ommetje maken" },
        //{ id: 100, question: "κάνω ηλιοθεραπεία", answer: "zonnebaden" },
        //{ id: 101, question: "κάνω καμάκι", answer: "flirten" },
        //{ id: 102, question: "κάνω κουβέντα", answer: "een babbeltje maken" },
        //{ id: 103, question: "κάνω μπάνιο", answer: "zwemmen" },
        //{ id: 104, question: "κάνω πλάκα", answer: "een grapje maken" },
        //{ id: 105, question: "κάνω ψώνια", answer: "boodschappen doen" },
        //{ id: 106, question: "καταλαβαίνω", answer: "ik begrijp, begrijpen" },
        //{ id: 107, question: "καφεδάκι, το", answer: "kopje Griekse koffie" },
        //{ id: 108, question: "κεφτεδάκι, το", answer: "gehaktballetje" },
        //{ id: 109, question: "κοντά", answer: "dichtbij" },
        //{ id: 110, question: "Κρήτη, η", answer: "Kreta" },
        //{ id: 111, question: "λοιπόν", answer: "dus, nou" },
        //{ id: 112, question: "μάθημα, το", answer: "de les" },
        //{ id: 113, question: "μακριά", answer: "ver weg" },
        //{ id: 114, question: "με", answer: "met" },
        //{ id: 115, question: "μεγάλος", answer: "groot" },
        //{ id: 116, question: "μένω", answer: "ik woon, wonen" },
        //{ id: 117, question: "μήνας, ο", answer: "de maand" },
        //{ id: 118, question: "μικρός", answer: "klein" },
        //{ id: 119, question: "μπακλαβάς, ο", answer: "bladerdeeggebak" },
        //{ id: 120, question: "μουσείο, το", answer: "het museum" },
        //{ id: 121, question: "μουσική, η", answer: "de muziek" },
        //{ id: 122, question: "μπαλκόνι, το", answer: "het balkon" },
        //{ id: 123, question: "νούμερο, το", answer: "het cijfer, (telefoon)nummer" },
        //{ id: 124, question: "ντοματoσαλάτα, η", answer: "tomaatsalade" },
        //{ id: 125, question: "όνειρο, το", answer: "de droom" },
        //{ id: 126, question: "παγωτό, το", answer: "het ijsje" },
        //{ id: 127, question: "παστίτιο, το", answer: "pastagerecht uit de oven" },
        //{ id: 128, question: "Πάτρα, η", answer: "Patras" },
        //{ id: 129, question: "περιμένω", answer: "ik wacht, wachten" },
        //{ id: 130, question: "πιπέρι, το", answer: "de peper" },
        //{ id: 131, question: "πού", answer: "waar" },
        //{ id: 132, question: "πώς", answer: "hoe" },
        //{ id: 133, question: "ραδιόφωνο, το", answer: "radio" },
        //{ id: 134, question: "σε", answer: "naar, in, op bij, aan, tegen, om" },
        //{ id: 135, question: "σελίδα, η", answer: "bladzijde" },
        //{ id: 136, question: "σήμερα", answer: "vandaag" },
        //{ id: 137, question: "σιγά σιγά", answer: "langzaam, zachtjes, rustig, voorzichtig" },
        //{ id: 138, question: "σκύλος, ο", answer: "de hond" },
        //{ id: 139, question: "στάση, η", answer: "de halte" },
        //{ id: 140, question: "Σύνταγμα, το", answer: "het Syntagma-plein" },
        //{ id: 141, question: "τηλέφωνο, το", answer: "de telefoon" },
        //{ id: 142, question: "τράπεζα, η", answer: "de (geld)bank" },
        //{ id: 143, question: "τραπέζι, το", answer: "de tafel" },
        //{ id: 144, question: "τώρα", answer: "nu" },
        //{ id: 145, question: "ύπνος, ο", answer: "de slaap" },
        //{ id: 146, question: "φίδι, το", answer: "de slang" },
        //{ id: 147, question: "φωτογραφεία, η", answer: "de foto" },
        //{ id: 148, question: "χάρτης, ο", answer: "de plattegrond" },
        //{ id: 149, question: "χτες", answer: "gisteren" },
        //{ id: 150, question: "χωριάτικη, η", answer: "de boerensalade" },
        //{ id: 151, question: "ώρα, η", answer: "de tijd/ het uur" },
        //{ id: 152, question: "Καλό μήνα!", answer: "Goede maand!" },
        //{ id: 153, question: "Καλό ύπνο!", answer: "Welterusten!" },
        //{ id: 154, question: "Θαύμα!", answer: "Geweldig!" },
        //{ id: 155, question: "Όνειρα γλυκά!", answer: "Zoete dromen!" },

        //// III
        //{ id: 156, question: "αγελάδα, η", answer: "de koe" },
        //{ id: 157, question: "αγόρι, το", answer: "de jongen" },
        //{ id: 158, question: "άλογο, το", answer: "het paard" },
        //{ id: 159, question: "άνθρωπος, ο", answer: "de mens" },
        //{ id: 160, question: "αργά", answer: "langzaam, laat" },
        //{ id: 161, question: "αρνί, το", answer: "het lam" },
        //{ id: 162, question: "άσπρος", answer: "wit" },
        //{ id: 163, question: "άσχημος", answer: "lelijk" },
        //{ id: 164, question: "αυγό, το", answer: "het ei" },
        //{ id: 165, question: "αυτός/ αυτή/ αυτό", answer: "deze, die, dit, dat/ hij, zij, het" },
        //{ id: 166, question: "βάλιτσα, η", answer: "de koffer" },
        //{ id: 167, question: "βλέπω", answer: "zien" },
        //{ id: 168, question: "γάλα, το", answer: "de melk" },
        //{ id: 169, question: "γαλάζιος", answer: "lichtblauw" },
        //{ id: 170, question: "γιατί", answer: "waarom/ omdat, want" },
        //{ id: 171, question: "γιατρός, ο", answer: "de arts" },
        //{ id: 172, question: "γιος, ο", answer: "de zoon" },
        //{ id: 173, question: "γκρίζος", answer: "grijs" },
        //{ id: 174, question: "γραβάτα, η", answer: "stropdas" },
        //{ id: 175, question: "γραμματόσημο, το", answer: "de postzegel" },
        //{ id: 176, question: "γραφείο, το", answer: "het bureau, het kantoor" },
        //{ id: 177, question: "γράφω", answer: "schrijven" },
        //{ id: 178, question: "γυναίκα, η", answer: "de vrouw" },
        //{ id: 179, question: "δασκάλα, η", answer: "de lerares" },
        //{ id: 180, question: "δάσκαλος, ο", answer: "de leraar" },
        //{ id: 181, question: "δέντρο, το", answer: "de boom" },
        //{ id: 182, question: "δημοκρατία, η", answer: "de democratie" },
        //{ id: 183, question: "διαβάζω", answer: "lezen" },
        //{ id: 184, question: "διαβατήριο, το", answer: "paspoort" },
        //{ id: 185, question: "δολάριο, το", answer: "de dollar" },
        //{ id: 186, question: "δουλεύω", answer: "werken" },
        //{ id: 187, question: "δράμα, το", answer: "het drama" },
        //{ id: 188, question: "δραχμή, η", answer: "de drachme" },
        //{ id: 189, question: "εκκλησία, η", answer: "de kerk" },
        //{ id: 190, question: "Ελλάδα, η", answer: "Griekenland" },
        //{ id: 191, question: "Έλληνας, ο", answer: "de Griek" },
        //{ id: 192, question: "Ελληνίδα, η", answer: "de Griekse" },
        //{ id: 193, question: "Ελληνικά, τα", answer: "het Grieks" },
        //{ id: 194, question: "έξω", answer: "buiten" },
        //{ id: 195, question: "εποχή, η", answer: "het seizoen/ het tijdperk" },
        //{ id: 196, question: "Ευρώπη, η", answer: "Europa" },
        //{ id: 197, question: "εφημερίδα, η", answer: "de krant" },
        //{ id: 198, question: "ζακέτα, η", answer: "het jasje" },
        //{ id: 199, question: "ζεστός", answer: "warm, heet" },
        //{ id: 200, question: "ζωή, η", answer: "het leven" },
        //{ id: 201, question: "ζωό, το", answer: "het dier" },
        //{ id: 202, question: "ήλιος, ο", answer: "de zon" },
        //{ id: 203, question: "θέατρο, το", answer: "het theater" },
        //{ id: 204, question: "κάθε", answer: "ieder, elk" },
        //{ id: 205, question: "καρέκλα, η", answer: "de stoel" },
        //{ id: 206, question: "κατσίκι, το", answer: "de geit" },
        //{ id: 207, question: "κεφάλι, το", answer: "het hoofd" },
        //{ id: 208, question: "κήπος, ο", answer: "de tuin" },
        //{ id: 209, question: "κίτρινος", answer: "geel" },
        //{ id: 210, question: "κόκορας, ο", answer: "de haan" },
        //{ id: 211, question: "κόκκινος", answer: "rood" },
        //{ id: 212, question: "κοντός", answer: "klein, kort, gedrongen" },
        //{ id: 213, question: "κόρη, η", answer: "de dochter" },
        //{ id: 214, question: "κορίτσι, το", answer: "het meisje" },
        //{ id: 215, question: "κόσμος, ο", answer: "de mensen/ de wereld/ de kosmos" },
        //{ id: 216, question: "κότα, η", answer: "de kip" },
        //{ id: 217, question: "κοτόπουλο, το", answer: "de kip (op je bord)" },
        //{ id: 218, question: "κουβεντιάζω", answer: "babbelen" },
        //{ id: 219, question: "κουτάλι, το", answer: "de lepel" },
        //{ id: 220, question: "κρίμα, το", answer: "jammer/ de zonde" },
        //{ id: 221, question: "κρύος", answer: "koud" },
        //{ id: 222, question: "κυρία, η", answer: "de mevrouw, de dame" },
        //{ id: 223, question: "κύριος, ο", answer: "de meneer, de heer" },
        //{ id: 224, question: "κωμωδία, η", answer: "de komedie" },
        //{ id: 225, question: "λεωφορείο, το", answer: "de bus" },
        //{ id: 226, question: "λουκάνικο, το", answer: "het worstje" },
        //{ id: 227, question: "μαγαζί, το", answer: "de winkel, de zaak" },
        //{ id: 228, question: "μάθημα, το", answer: "de les" },
        //{ id: 229, question: "μαθητής, ο", answer: "de leerling" },
        //{ id: 230, question: "μαθήτρια, η", answer: "de leerlinge" },
        //{ id: 231, question: "μαύρος", answer: "zwart" },
        //{ id: 232, question: "μαχαίρι, το", answer: "het mes" },
        //{ id: 233, question: "μέσα", answer: "binnen, vanbinnen" },
        //{ id: 234, question: "μητέρα, η", answer: "de moeder" },
        //{ id: 235, question: "μοβ", answer: "paars" },
        //{ id: 236, question: "μπάλα, η", answer: "de bal" },
        //{ id: 237, question: "μπάνιο, το", answer: "de badkamer" },
        //{ id: 238, question: "μπλε", answer: "blauw" },
        //{ id: 239, question: "μπλούζα, η", answer: "de blouse" },
        //{ id: 240, question: "μπλουζάκι, το", answer: "t-shirt" },
        //{ id: 241, question: "μπουκάλι, το", answer: "de fles" },
        //{ id: 242, question: "νησί, το", answer: "het eiland" },
        //{ id: 243, question: "νομίζω", answer: "denken, geloven, vinden" },
        //{ id: 244, question: "νωρίς", answer: "vroeg" },
        //{ id: 245, question: "ξενοδοχείο, το", answer: "het hotel" },
        //{ id: 246, question: "ξένος, ο", answer: "de vreemdeling, de buitenlander" },
        //{ id: 247, question: "ξέρω", answer: "weten, kennen, kunnen" },
        //{ id: 248, question: "Ολλανδέζα, η", answer: "de Nederlandse" },
        //{ id: 249, question: "Ολλανδία, η", answer: "Nederland" },
        //{ id: 250, question: "Ολλανδικά, τα", answer: "Het Nederlands" },
        //{ id: 251, question: "Ολλανδός, ο", answer: "de Nederlander" },
        //{ id: 252, question: "όμορφος", answer: "mooi, knap, fraai" },
        //{ id: 253, question: "παντελόνι, το", answer: "de broek" },
        //{ id: 254, question: "παράθυρο, το", answer: "het raam" },
        //{ id: 255, question: "παρέα, η", answer: "het gezelschap, de vriendenkring" },
        //{ id: 256, question: "Πάσχα, το", answer: "het Paasfeest" },
        //{ id: 257, question: "πατέρας, ο", answer: "de vader" },
        //{ id: 258, question: "περιοδικό, το", answer: "het tijdschrift" },
        //{ id: 259, question: "περιπτεράς, ο", answer: "de kioskhouder" },
        //{ id: 260, question: "περίπτερο, το", answer: "de kiosk" },
        //{ id: 261, question: "πιρούνι, το", answer: "de vork" },
        //{ id: 262, question: "πηγαίνω", answer: "gaan" },
        //{ id: 263, question: "πλατεία, η", answer: "het plein" },
        //{ id: 264, question: "πληρώνω", answer: "betalen" },
        //{ id: 265, question: "πόδι, το", answer: "de been/ de voet" },
        //{ id: 266, question: "ποδόσφαιρο, το", answer: "de voetbal" },
        //{ id: 267, question: "πολιτική, η", answer: "de politiek" },
        //{ id: 268, question: "ποντίκι, το", answer: "de muis" },
        //{ id: 269, question: "πόρτα, η", answer: "de deur" },
        //{ id: 270, question: "πορτοκαλί", answer: "oranje" },
        //{ id: 271, question: "πόσο", answer: "hoezeer, hoeveel" },
        //{ id: 272, question: "πότε", answer: "wanneer" },
        //{ id: 273, question: "ποτήρι, το", answer: "het glas" },
        //{ id: 274, question: "πουκάμισο, το", answer: "het overhemd" },
        //{ id: 275, question: "πράγμα, το", answer: "het ding, het voorwerp" },
        //{ id: 276, question: "πράσινος", answer: "groen" },
        //{ id: 277, question: "πρόβατο, το", answer: "het schaap" },
        //{ id: 278, question: "ροζ", answer: "roze" },
        //{ id: 279, question: "σαββατοκύριακο, το", answer: "het weekend" },
        //{ id: 280, question: "σελίδα, η", answer: "de bladzijde" },
        //{ id: 281, question: "σούπερ-μάρκετ, το", answer: "de supermarkt" },
        //{ id: 282, question: "σπανακόπιτα, η", answer: "spinaziebroodje van bladerdeeg" },
        //{ id: 283, question: "στάδιο, το", answer: "het stadion" },
        //{ id: 284, question: "συγνώμη", answer: "sorry, pardon" },
        //{ id: 285, question: "σχολείο, το", answer: "de school" },
        //{ id: 286, question: "ταχυδρομείο, το", answer: "het postkantoor" },
        //{ id: 287, question: "τηγανιτός", answer: "gebakken, gefrituurd" },
        //{ id: 288, question: "τηλεόραση, η", answer: "de televisie" },
        //{ id: 289, question: "τι", answer: "wat, wat voor" },
        //{ id: 290, question: "τίποτα", answer: "niets/ iets" },
        //{ id: 291, question: "τυρόπιτα, η", answer: "fetabroodje van bladerdeeg" },
        //{ id: 292, question: "τραγωδία, η", answer: "de tragedie" },
        //{ id: 293, question: "φαρμακείο, το", answer: "de apotheek" },
        //{ id: 294, question: "φεγγάρι, το", answer: "de maan" },
        //{ id: 295, question: "φθινόπωρο, το", answer: "de herfst" },
        //{ id: 296, question: "φίλη, η", answer: "de vriendin" },
        //{ id: 297, question: "φίλος, ο", answer: "de vriend" },
        //{ id: 298, question: "φούρνος, ο", answer: "de bakkerij/ de oven" },
        //{ id: 299, question: "φρέσκος", answer: "vers, fris" },
        //{ id: 300, question: "χαρά, η", answer: "de vreugde" },
        //{ id: 301, question: "χειμώνας, ο", answer: "de winter" },
        //{ id: 302, question: "χέρι, το", answer: "de arm, de hand" },
        //{ id: 303, question: "χρώμα, το", answer: "de kleur" },
        //{ id: 304, question: "ψάρι, το", answer: "de vis" },
        //{ id: 305, question: "ψηλός", answer: "hoog, lang" },
        //{ id: 306, question: "Πόσο κάνει;", answer: "Hoeveel kost het?" },
        //{ id: 307, question: "Καλώς όρισες!", answer: "Welkom!" },
        //{ id: 308, question: "Κρίμα!", answer: "Jammer!" },
        //{ id: 309, question: "Τα πράγματα", answer: "de bagage" },

        //// IV
        //{ id: 310, question: "αγαπάω", answer: "houden van, liefhebben" },
        //{ id: 311, question: "αγορά, η", answer: "de markt" },
        //{ id: 312, question: "αγοράζω", answer: "kopen" },
        //{ id: 313, question: "αδερφή, η", answer: "de zus" },
        //{ id: 314, question: "αδερφός, ο", answer: "de broer" },
        //{ id: 315, question: "ακριβός", answer: "duur" },
        //{ id: 316, question: "αλλά", answer: "maar" },
        //{ id: 317, question: "άλογο, το", answer: "het paard" },
        //{ id: 318, question: "ανεβαίνω", answer: "naar boven gaan, beklimmen" },
        //{ id: 319, question: "ανοιχτός", answer: "open, geopend" },
        //{ id: 320, question: "ανοίγω", answer: "open doen" },
        //{ id: 321, question: "απέναντι", answer: "aan de overkant, tegenover" },
        //{ id: 322, question: "απόγευμα, το", answer: "de namiddag" },
        //{ id: 323, question: "αριστερά", answer: "links" },
        //{ id: 324, question: "αρκετός", answer: "voldoende, genoeg/ aardig wat" },
        //{ id: 325, question: "αρχίζω", answer: "beginnen" },
        //{ id: 326, question: "αρχιτέκτονας, ο", answer: "de architect" },
        //{ id: 327, question: "ασανσέρ, το", answer: "de lift" },
        //{ id: 328, question: "αστείο, το", answer: "de grap, de mop" },
        //{ id: 329, question: "αστείος", answer: "grappig, leuk, belachelijk" },
        //{ id: 330, question: "αχλάδι, το", answer: "de peer" },
        //{ id: 331, question: "βάρκα, η", answer: "boot" },
        //{ id: 332, question: "βεβαίως", answer: "jazeker, zeker, natuurlijk" },
        //{ id: 333, question: "βραδινό, το", answer: "het avondeten" },
        //{ id: 334, question: "βράδυ, το", answer: "de avond" },
        //{ id: 335, question: "γήπεδο, το", answer: "sportveld, voetbalveld, stadion" },
        //{ id: 336, question: "γκρινιάζω", answer: "mopperen, klagen, zeuren" },
        //{ id: 337, question: "γλυκός", answer: "zoet/ lief, zacht" },
        //{ id: 338, question: "γωνία, η", answer: "de hoek" },
        //{ id: 339, question: "δεξιά", answer: "rechts" },
        //{ id: 340, question: "δέμα, το", answer: "het postpakket" },
        //{ id: 341, question: "δίκλινο, το", answer: "tweepersoonskamer" },
        //{ id: 342, question: "δωμάτιο, το", answer: "de kamer" },
        //{ id: 343, question: "εκείνος", answer: "die daar, dat daar/ hij, zij het" },
        //{ id: 344, question: "ελεύθερος", answer: "vrij" },
        //{ id: 345, question: "ηθοποιός, ο", answer: "de acteur" },
        //{ id: 346, question: "ίσως", answer: "misschien" },
        //{ id: 347, question: "καθαρίζω", answer: "schoon maken" },
        //{ id: 348, question: "καθαριστήριο, το", answer: "de wasserette" },
        //{ id: 349, question: "καθαρός", answer: "schoon, helder/ duidelijk" },
        //{ id: 350, question: "καθηγητής, ο", answer: "de docent, professor" },
        //{ id: 351, question: "καθηγήτρια, η", answer: "de docente, professor" },
        //{ id: 352, question: "καθόλου", answer: "helemaal niet, geenszins" },
        //{ id: 353, question: "καπετάνιος, ο", answer: "de kapitein" },
        //{ id: 354, question: "κάποτε", answer: "ooit, eens" },
        //{ id: 355, question: "καπνίζω", answer: "roken" },
        //{ id: 356, question: "καράβι, το", answer: "boot, schip" },
        //{ id: 357, question: "κατάστημα, το", answer: "zaak, winkel, filiaal, warenhuis" },
        //{ id: 358, question: "κατεβαίνω", answer: "naar beneden gaan , afdalen" },
        //{ id: 359, question: "κάτω", answer: "onder, beneden" },
        //{ id: 360, question: "κεράσι, το", answer: "de kers" },
        //{ id: 361, question: "κινηματογράφος, ο", answer: "de bioscoop" },
        //{ id: 362, question: "κλείνω", answer: "sluiten, dichtdoen" },
        //{ id: 363, question: "κλειστός", answer: "dicht, gesloten" },
        //{ id: 364, question: "κοπέλα, η", answer: "meisje" },
        //{ id: 365, question: "κουρασμένος", answer: "vermoeid" },
        //{ id: 366, question: "κρεβάτι , το", answer: "bed" },
        //{ id: 367, question: "λεπτό, το", answer: "minuut/ cent" },
        //{ id: 368, question: "λεφτά, τα", answer: "het geld" },
        //{ id: 369, question: "λιμάνι, το", answer: "de haven" },
        //{ id: 370, question: "μέλι, το", answer: "de honing" },
        //{ id: 371, question: "μέλισσα, η", answer: "de bij" },
        //{ id: 372, question: "μεσημέρι, το", answer: "de middag (midden op de dag)" },
        //{ id: 373, question: "μεσημεριανό, το", answer: "het middageten, de lunch" },
        //{ id: 374, question: "μετράω", answer: "tellen, meten" },
        //{ id: 375, question: "μέτριος", answer: "matig, beetje (suiker in de koffie)" },
        //{ id: 376, question: "μήπως", answer: "misschien (in vraagzin)" },
        //{ id: 377, question: "μιλάω", answer: "spreken, praten" },
        //{ id: 378, question: "μολύβι, το", answer: "het potlood" },
        //{ id: 379, question: "μονόκλινο, το", answer: "eenpersoonskamer" },
        //{ id: 380, question: "μπλούζα, η", answer: "de bloes" },
        //{ id: 381, question: "νέα, τα", answer: "het nieuws, de nieuwtjes" },
        //{ id: 382, question: "νέος, ο", answer: "jong, nieuw" },
        //{ id: 383, question: "νομίζω", answer: "vinden, denken, geloven, menen" },
        //{ id: 384, question: "ξύλο, το", answer: "het hout" },
        //{ id: 385, question: "ξυπνάω", answer: "wakker worden" },
        //{ id: 386, question: "όμως", answer: "echter" },
        //{ id: 387, question: "όνομα, το", answer: "de naam" },
        //{ id: 388, question: "όρεξη, η", answer: "eetlust" },
        //{ id: 389, question: "όροφος, ο", answer: "de etage" },
        //{ id: 390, question: "παίζω", answer: "spelen" },
        //{ id: 391, question: "πακέτο, το", answer: "het pakket" },
        //{ id: 392, question: "πανεπιστήμιο, το", answer: "de universiteit" },
        //{ id: 393, question: "παντελόνι, το", answer: "de broek" },
        //{ id: 394, question: "παντρεμένος", answer: "getrouwd" },
        //{ id: 395, question: "πάνω", answer: "op, bovenop" },
        //{ id: 396, question: "παρακάτω", answer: "verderop" },
        //{ id: 397, question: "παραλία, η", answer: "het strand, de kust, de boulevard" },
        //{ id: 398, question: "περπατάω", answer: "lopen, wandelen" },
        //{ id: 399, question: "πλοίο, το", answer: "de boot, het schip" },
        //{ id: 400, question: "πλούσιος", answer: "rijk" },
        //{ id: 401, question: "ποιος/ ποια/ ποιο", answer: "wie, welke" },
        //{ id: 402, question: "πόλη, η", answer: "de stad" },
        //{ id: 403, question: "πότε", answer: "wanneer" },
        //{ id: 404, question: "ποτέ", answer: "nooit, nimmer/ ooit, wel eens" },
        //{ id: 405, question: "πού και πού", answer: "af en toe" },
        //{ id: 406, question: "πούρο, το", answer: "de sigaar" },
        //{ id: 407, question: "προτιμάω", answer: "prefereren, liever willen" },
        //{ id: 408, question: "πρωί, το", answer: "de ochtend" },
        //{ id: 409, question: "πρωινό, το", answer: "het ontbijt" },
        //{ id: 410, question: "ρέστα, τα", answer: "het wisselgeld" },
        //{ id: 411, question: "ρόλος, ο", answer: "de rol" },
        //{ id: 412, question: "σινεμά, το", answer: "de cinema" },
        //{ id: 413, question: "σκέτος", answer: "puur/ zonder suiker (in de koffie)" },
        //{ id: 414, question: "σοκολάτα, η", answer: "de chocola" },
        //{ id: 415, question: "σπίρτο, το", answer: "de lucifers" },
        //{ id: 416, question: "στρίβω", answer: "draaien, rollen/ afslaan" },
        //{ id: 417, question: "συναυλία, η", answer: "het concert" },
        //{ id: 418, question: "τάβλι, το", answer: "triktrak spel" },
        //{ id: 419, question: "ταινία, η", answer: "de film/ de band" },
        //{ id: 420, question: "ταξιδεύω", answer: "reizen" },
        //{ id: 421, question: "ταξίδι, το", answer: "de reis" },
        //{ id: 422, question: "τελειώνω", answer: "beëindigen, stoppen, voltooien" },
        //{ id: 423, question: "τέλος, το", answer: "het einde" },
        //{ id: 424, question: "τετράγωνο, το", answer: "vierkant, (huizen)blok" },
        //{ id: 425, question: "τηλεφωνάω", answer: "bellen, telefoneren" },
        //{ id: 426, question: "τραγουδάω", answer: "zingen" },
        //{ id: 427, question: "τραγούδι, το", answer: "het lied" },
        //{ id: 428, question: "τσιγάρο, το", answer: "sigaret" },
        //{ id: 429, question: "υπάλληλος, ο/η", answer: "bediende, medewerker, beambte" },
        //{ id: 430, question: "φαγητό, το", answer: "het voedsel, het eten" },
        //{ id: 431, question: "φοιτητής, ο", answer: "de student" },
        //{ id: 432, question: "φοιτήτρια, η", answer: "de studente" },
        //{ id: 433, question: "φτηνός", answer: "goedkoop" },
        //{ id: 434, question: "φτωχός", answer: "arm" },
        //{ id: 435, question: "φωνάζω", answer: "roepen, schreeuwen" },
        //{ id: 436, question: "χρόνος, ο", answer: "de tijd/ het jaar" },
        //{ id: 437, question: "χωριό, το", answer: "het dorp" },
        //{ id: 438, question: "ψιλά, τα", answer: "het kleingeld" },
        //{ id: 439, question: "Θες (θέλεις) ξύλο;", answer: "Zoek je ruzie?" },
        //{ id: 440, question: "Θα φας ξύλο!", answer: "Je krijgt zo een pak slaag!" },
        //{ id: 441, question: "Καλό ταξίδι!", answer: "Goede reis!" },

        //// V
        //{ id: 442, question: "ακριβώς", answer: "precies, exact" },
        //{ id: 443, question: "ανθρωπολογία", answer: "antropologie" },
        //{ id: 444, question: "απαντάω", answer: "antwoorden" },
        //{ id: 445, question: "απάντηση, η", answer: "het antwoord" },
        //{ id: 446, question: "απλό, το", answer: "het enkeltje" },
        //{ id: 447, question: "απλός", answer: "eenvoudig, simpel" },
        //{ id: 448, question: "αρχαιολογία, η", answer: "archeologie" },
        //{ id: 449, question: "αρχιτέκτονική, η", answer: "architectuur" },
        //{ id: 450, question: "αστρολογία, η", answer: "astrologie" },
        //{ id: 451, question: "αυλή, η", answer: "de binnenplaats, hof" },
        //{ id: 452, question: "βιολί, το", answer: "de viool" },
        //{ id: 453, question: "γειτονιά, η", answer: "de buurt, de wijk" },
        //{ id: 454, question: "γεωγραφία, η", answer: "geografie" },
        //{ id: 455, question: "γίνομαι", answer: "worden, gebeuren" },
        //{ id: 456, question: "γυρίζω", answer: "keren, draaien, terugkomen" },
        //{ id: 457, question: "δαμάσκηνο, το", answer: "de pruim" },
        //{ id: 458, question: "διασκεδάζω", answer: "(zich) vermaken" },
        //{ id: 459, question: "διψάω", answer: "dorst hebben" },
        //{ id: 460, question: "εισιτήριο, το", answer: "het kaartje, ticket, entree" },
        //{ id: 461, question: "επιστροφή, η (με)", answer: "terugreis/ retourtje" },
        //{ id: 462, question: "εργοστάσιο, το", answer: "de fabriek" },
        //{ id: 463, question: "εργάτης, ο", answer: "de arbeider" },
        //{ id: 464, question: "έργο, το", answer: "het werk/ het stuk, de film, het oeuvre" },
        //{ id: 465, question: "ερώτηση, η", answer: "de vraag" },
        //{ id: 466, question: "εστιατόριο, το", answer: "het restaurant" },
        //{ id: 467, question: "ετοιμάζω", answer: "klaarmaken, bereiden" },
        //{ id: 468, question: "θεία, η", answer: "de tante" },
        //{ id: 469, question: "θείος, ο", answer: "de oom" },
        //{ id: 470, question: "ιστορία, η", answer: "de geschiedenis, het verhaal" },
        //{ id: 471, question: "κανένας/ καμία/ κανένα", answer: "iemand, een-of ander/ niemand, geen enkele" },
        //{ id: 472, question: "καρπούζι, το", answer: "de watermeloen" },
        //{ id: 473, question: "κιθάρα, η", answer: "de gitaar" },
        //{ id: 474, question: "κλαρίνο, το", answer: "de klarinet" },
        //{ id: 475, question: "λάθος, το", answer: "de fout, de vergissing" },
        //{ id: 476, question: "λαογραφία, η", answer: "de folklore" },
        //{ id: 477, question: "λέξη, η", answer: "het woord" },
        //{ id: 478, question: "λεξικό, το", answer: "het woordenboek" },
        //{ id: 479, question: "μελετάω", answer: "bestuderen" },
        //{ id: 480, question: "μήλο, το", answer: "de appel" },
        //{ id: 481, question: "μισός, ο", answer: "de helft" },
        //{ id: 482, question: "ξαδέρφη, η", answer: "de nicht" },
        //{ id: 483, question: "ξάδερφος, ο", answer: "de neef" },
        //{ id: 484, question: "ξηρός", answer: "dor, droog (ook voor wijn)" },
        //{ id: 485, question: "ξίδι, το", answer: "azijn" },
        //{ id: 486, question: "ξινός", answer: "zuur, wrang" },
        //{ id: 487, question: "οικογένεια, η", answer: "de familie, het gezin" },
        //{ id: 488, question: "ούτε", answer: "noch, ook niet, evenmin" },
        //{ id: 489, question: "παντού", answer: "overal" },
        //{ id: 490, question: "πεπόνι, το", answer: "de suikermeloen" },
        //{ id: 491, question: "πιάνο, το", answer: "de piano" },
        //{ id: 492, question: "πεινάω", answer: "honger hebben" },
        //{ id: 493, question: "πειράζω", answer: "plagen, treiteren, storen" },
        //{ id: 494, question: "πολυκατοικία, η", answer: "het flatgebouw" },
        //{ id: 495, question: "Πρωτομαγιά, η", answer: "1 mei (bloemenfeest)" },
        //{ id: 496, question: "Πρωτοχρονιά, η", answer: "nieuwjaarsdag" },
        //{ id: 497, question: "ρόδι, το", answer: "de granaatappel" },
        //{ id: 498, question: "ρωτάω", answer: "vragen naar" },
        //{ id: 499, question: "σπουδάζω", answer: "een studie volgen, studeren" },
        //{ id: 500, question: "σπουδαίος", answer: "belangrijk, gewichtig" },
        //{ id: 501, question: "σταματάω", answer: "stoppen, tegenhouden" },
        //{ id: 502, question: "σωστός", answer: "juist, correct" },
        //{ id: 503, question: "τέταρτο, το", answer: "het kwart, kwartier" },
        //{ id: 504, question: "τόπος, ο", answer: "de plek, de plaats" },
        //{ id: 505, question: "τουριστική θέση, η", answer: "tweede klas" },
        //{ id: 506, question: "υπάρχω", answer: "bestaan" },
        //{ id: 507, question: "φεύγω", answer: "vertrekken, weggaan" },
        //{ id: 508, question: "φράουλα, η", answer: "de aardbei" },
        //{ id: 509, question: "χαιρετισμός, ο", answer: "begroeting, groet" },
        //{ id: 510, question: "χαίρω", answer: "zich verheugen, genieten" },
        //{ id: 511, question: "χαρά, η", answer: "de vreugde" },
        //{ id: 512, question: "χαρούμενος", answer: "blij, vrolijk" },
        //{ id: 513, question: "χορός, ο", answer: "de dans" },
        //{ id: 514, question: "Χριστούγεννα, τα", answer: "Kerst" },
        //{ id: 515, question: "Δεν πειράζει.", answer: "Het geeft niet." },
        //{ id: 516, question: "Χαιρετίσματα σε...", answer: "Groetjes aan …" },
        //{ id: 517, question: "Χαιρετισμούς σε...", answer: "Groeten aan …" },
        //{ id: 518, question: "Χαίρω πολύ.", answer: "Aangenaam kennis te maken" },

        //// VI
        //{ id: 519, question: "άγια, η", answer: "de heilige (vr)" },
        //{ id: 520, question: "άγιος, ο", answer: "de heilige (mnl)" },
        //{ id: 521, question: "αιτιατική, η", answer: "vierde naamval/ lijdend voorwerp" },
        //{ id: 522, question: "ακούω", answer: "horen, luisteren" },
        //{ id: 523, question: "αποχαιρετώ", answer: "gedag zeggen, afscheid nemen" },
        //{ id: 524, question: "αρέσω", answer: "bevallen, aanstaan, aanspreken" },
        //{ id: 525, question: "αργώ", answer: "te laat zijn, langzaam zijn" },
        //{ id: 526, question: "αρχαίος", answer: "oud, antiek" },
        //{ id: 527, question: "αχάριστος", answer: "ondankbaar" },
        //{ id: 528, question: "βρίσκω", answer: "vinden/ bedenken" },
        //{ id: 529, question: "γελάω", answer: "lachen" },
        //{ id: 530, question: "γεμιστά, τα", answer: "met rijst gevulde paprika's en tomaten" },
        //{ id: 531, question: "γενέθλια, τα", answer: "de verjaardag" },
        //{ id: 532, question: "γιορτάζω", answer: "vieren, feest vieren" },
        //{ id: 533, question: "γιορτή, η", answer: "het feest, de naamdag" },
        //{ id: 534, question: "δεσποινίς, η", answer: "de juffrouw, de jongedame" },
        //{ id: 535, question: "διαμέρισμα, το", answer: "het appartement" },
        //{ id: 536, question: "δύσκολος", answer: "moeilijk, lastig" },
        //{ id: 537, question: "δυστυχισμένος", answer: "ongelukkig" },
        //{ id: 538, question: "δυστυχώς", answer: "helaas, jammer genoeg" },
        //{ id: 539, question: "εικόνα, η", answer: "de ikoon, afbeelding" },
        //{ id: 540, question: "ελιά, η", answer: "de olijf, de olijfboom" },
        //{ id: 541, question: "ελαιόλαδο, το", answer: "de olijfolie" },
        //{ id: 542, question: "επείγον", answer: "met spoed/ de expresbrief" },
        //{ id: 543, question: "επίθετο, το", answer: "de achternaam" },
        //{ id: 544, question: "έρχομαι", answer: "komen" },
        //{ id: 545, question: "εύκολος", answer: "makkelijk" },
        //{ id: 546, question: "ευτυχισμένος", answer: "gelukkig" },
        //{ id: 547, question: "ευτυχώς", answer: "gelukkig maar" },
        //{ id: 548, question: "ευχαριστημένος", answer: "tevreden" },
        //{ id: 549, question: "θεά, η", answer: "de godin" },
        //{ id: 550, question: "θεός, ο", answer: "de god" },
        //{ id: 551, question: "θρησκεία, η", answer: "het geloof" },
        //{ id: 552, question: "θυμάμαι", answer: "zich herinneren" },
        //{ id: 553, question: "κάθομαι", answer: "zitten, gaan zitten" },
        //{ id: 554, question: "καλαμάρι, το", answer: "inktvisje" },
        //{ id: 555, question: "κλαίω", answer: "huilen" },
        //{ id: 556, question: "κλασσικός", answer: "klassiek, antiek" },
    ];

    // Create a shuffled version of the flashcards
    let shuffledCards = [];

    // Fisher-Yates shuffle algorithm function
    function shuffleArray(array: any) {
        // Create a copy of the original array to avoid modifying it
        const arrayCopy = [...array];
        // Start from the last element and swap it with a randomly selected element
        for (let i = arrayCopy.length - 1; i > 0; i--) {
            // Pick a random index from 0 to i
            const j = Math.floor(Math.random() * (i + 1));
            // Swap elements at i and j
            [arrayCopy[i], arrayCopy[j]] = [arrayCopy[j], arrayCopy[i]];
        }
        return arrayCopy;
    }

    // Initialize shuffled cards when component loads
    shuffledCards = shuffleArray(flashCards);

    // Keep track of the current card index
    let currentCardIndex = 0;

    // State for tracking points system
    let points = 0;
    let attempted = 0;

    // Function to go to the next card
    // Function to go to the next card
    function nextCard() {
        if (currentCardIndex < shuffledCards.length - 1) {
            currentCardIndex++;
        }
    }

    // Function to go to the previous card
    function prevCard() {
        if (currentCardIndex > 0) {
            currentCardIndex--;
        }
    }
    // Function to update points when an answer is submitted
    function handleAnswerSubmit(event: any) {
        const isCorrect = event.detail.isCorrect;
        attempted++;

        if (isCorrect) {
            points++; // Add 1 point for correct answer

            // Set a 2-second delay for correct answers before moving to the next card
            if (currentCardIndex < shuffledCards.length - 1) {
                setTimeout(() => {
                    nextCard();
                }, 2000);
            }
        } else {
            // No point deduction for incorrect answers

            // Set a 5-second delay for incorrect answers before moving to the next card
            if (currentCardIndex < shuffledCards.length - 1) {
                setTimeout(() => {
                    nextCard();
                }, 5000);
            }
        }
    }
</script>

<main>
    <div class="container">
        <h1>Καλή τύχη αγάπη μου</h1>

        <div class="score-container">
            <p>Points: {points} (Attempted: {attempted})</p>
        </div>

        <div class="card-container">
            <FlashCard
                flashCard={shuffledCards[currentCardIndex]}
                on:answerSubmitted={handleAnswerSubmit}
            />
        </div>

        <div class="navigation">
            <button on:click={prevCard} disabled={currentCardIndex === 0}
                >Previous</button
            >
            <span class="card-counter"
                >{currentCardIndex + 1} / {shuffledCards.length}</span
            >
            <button
                on:click={nextCard}
                disabled={currentCardIndex === shuffledCards.length - 1}
                >Next</button
            >
        </div>
    </div>
</main>

<style>
    :global(body) {
        background-color: #10abb4;
        color: #004c50;
        margin: 0;
        padding: 0;
        font-family:
            -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen-Sans,
            Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
    }

    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        max-width: 800px;
        margin: 0 auto;
        padding: 20px;
        background-color: white;
        border-radius: 12px;
        box-shadow: 0 4px 12px rgba(0, 76, 80, 0.1);
    }

    h1 {
        color: #004c50;
        margin-bottom: 20px;
        font-weight: 700;
        text-align: center;
    }

    .score-container {
        margin-bottom: 20px;
        font-size: 1.2rem;
        font-weight: bold;
        color: #004c50;
        background-color: rgba(16, 171, 180, 0.1);
        padding: 8px 16px;
        border-radius: 8px;
    }

    .card-container {
        width: 100%;
        margin-bottom: 20px;
    }

    .navigation {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        max-width: 400px;
        padding: 10px;
        background-color: rgba(0, 147, 156, 0.05);
        border-radius: 8px;
    }

    button {
        background-color: #00939c;
        color: white;
        border: none;
        padding: 10px 20px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        border-radius: 4px;
        transition: all 0.3s ease;
        font-weight: 500;
        box-shadow: 0 2px 4px rgba(0, 76, 80, 0.2);
    }

    button:hover {
        background-color: #10abb4;
        transform: translateY(-2px);
        box-shadow: 0 4px 8px rgba(0, 76, 80, 0.3);
    }

    button:disabled {
        background-color: rgba(0, 147, 156, 0.3);
        cursor: not-allowed;
        box-shadow: none;
        transform: none;
    }

    .card-counter {
        font-size: 1rem;
        color: #502000;
        font-weight: 600;
        background-color: rgba(156, 62, 0, 0.1);
        padding: 4px 10px;
        border-radius: 4px;
    }
</style>
