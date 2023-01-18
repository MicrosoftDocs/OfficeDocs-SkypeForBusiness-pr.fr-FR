---
title: Codes pays de routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lisez cet article pour rechercher les codes de pays du chemin d’accès multimédia pour le routage direct afin de pouvoir sélectionner le chemin d’accès multimédia optimal.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a70dad128987a5fb0df639984be07b623f9ff425
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812671"
---
# <a name="direct-routing-media-path-country-codes"></a>Codes de pays du chemin de média de routage direct

Lors du choix d’un chemin de routage pour le support, le routage direct, par défaut, affecte toujours un centre de données en fonction de l’adresse IP publique du contrôleur de bordure de session (SBC) et sélectionne toujours le chemin le plus proche du centre de données SBC.

Toutefois, dans certains cas, le chemin d’accès multimédia par défaut peut ne pas être le chemin d’accès multimédia optimal ; Par exemple, une adresse IP publique d’une plage États-Unis peut être affectée à un SBC situé en Europe. 

En utilisant le paramètre -MediaRelayRoutingLocationOverride avec les applets de commande New-CsOnlinePSTNGateway et Set-CsOnlinePSTNGateway, vous pouvez spécifier la région par défaut pour le trafic multimédia. Par exemple, la commande suivante spécifie que la région préférée est l’Allemagne :

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Notez que Microsoft recommande de définir ce paramètre uniquement si les journaux des appels indiquent clairement que l’affectation par défaut du centre de données pour le chemin d’accès multimédia n’utilise pas le chemin le plus proche du centre de données SBC. 
 
## <a name="country-code-reference-table"></a>Table de référence des codes de pays

Le tableau suivant montre les valeurs de code de pays pour le paramètre -MediaRelayRoutingLocationOverride :

| Pays         | Code 
|-----------------|--------------------|
| Afghanistan     | AF |
| Aland (îles)   | AX |
| Albanie         | AL |
| Algérie         | DZ |
| Samoa américaines  | COMME |
| Andorre         | AD |
| Angola          | AO |
| Anguilla        | IA |
| Antarctique      | AQ | 
| Antigua-et-Barbuda | AG |
| Argentine       | AR |
| Arménie         | SUIS |
| Aruba           | AW |
| Australie       | AU |
| Autriche         | À |
| Azerbaïdjan      | AZ |
| Bahamas         | BS |
| Bahreïn         | BH |
| Bangladesh      | BD |
| Barbade        | BB |
| Bélarus         | BY |
| Belgique         | BE |
| Belize          | BZ |
| Bénin           | BJ |
| Bermudes         | BM |
| Bhoutan          | BT |
| Bolivie         | BO |
| Bonaire         | BQ |
| Bosnie-Herzégovine | BA |
| Botswana        | BW |
| Île Bouvet   | BV |
| Brésil          | BR |
| Territoire britannique de l’océan Indien | IO |
| Îles Vierges britanniques | VG |
| Brunei          | BN |
| Bulgarie        | BG |
| Burkina Faso    | BF |
| Burundi         | BI |
| Cabo Verde      | CV |
| Cambodge        | KH |
| Cameroun        | CM |
| Canada          | CA |
| Îles Cayman  | KY |
| République centrafricaine | CF |
| Tchad            | TD |
| Chili           | CL |
| Chine           | CN |
| Christmas Island | CX |
| Îles Cocos (Keeling) | CC |
| Colombie        | CO |
| Comores         | KM |
| Congo           | CG |
| Congo (RDC)     | CD |
| Cook (îles)    | CK |
| Costa Rica      | CR |
| Côte d’Ivoire   | CI |
| Croatie         | HR |
| Cuba            | CU |
| Curaçao         | CW |
| Chypre          | CY |
| Tchéquie         | CZ |
| Danemark         | DK |
| Djibouti        | DJ |
| Dominique        | DM |
| République dominicaine | FAIRE |
| Équateur         | EC |
| Égypte           | EG |
| Salvador     | SV |
| Guinée Équatoriale | GQ |
| Érythrée         | ER |
| Estonie         | EE |
| Eswatini        | SZ |
| Éthiopie        | ET |
| Îles Malouines | FK |
| Îles Féroé   | FO |
| Fidji            | FJ |
| Finlande         | FI |
| France          | FR |
| Guyane française   | GF |
| Polynésie française | PF |
| Français Territoires du Sud | TF |
| Gabon           | GA |
| Gambie          | GM |
| Géorgie         | GE |
| Allemagne         | DE |
| Ghana           | GH |
| Gibraltar       | GI |
| Grèce          | GR |
| Groenland       | GL |
| Grenade         | GD |
| Guadeloupe      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernesey        | GG |
| Guinée          | GN |
| Guinea-Bissau   | GW |
| Guyane          | GY |
| Haïti           | SALUT |
| Îles Heard et McDonald | HM |
| Honduras        | HN |
| Hong Kong (R.A.S)   | HK |
| Hongrie         | HU |
| Islande         | EST |
| Inde           | DANS |
| Indonésie       | ID |
| Iran            | IR |
| Irak            | IQ |
| Irlande         | IE |
| Île de Man     | MI |
| Israël          | IL |
| Italie           | IT |
| Jamaïque         | JM |
| Jan Mayen       | XJ |
| Japon           | JP |
| Jersey          | JE |
| Jordanie          | JO |
| Kazakhstan      | KZ |
| Kenya           | KE |
| Kiribati        | KI |
| Corée           | KR |
| Kosovo          | XK |
| Koweït          | KW |
| Kirghizstan      | KG |
| Laos            | LA |
| Lettonie          | LV |
| Liban         | LB |
| Lesotho         | LS |
| Libéria         | LR |
| Libye           | LY |
| Liechtenstein   | LI |
| Lituanie       | LT |
| Luxembourg      | LU |
| Macao (R.S.)       | MO |
| Madagascar      | MG |
| Malawi          | MW |
| Malaisie        | MY |
| Maldives        | MV |
| Mali            | ML |
| Malte           | MT |
| Îles Marshall | MH |
| Martinique      | MQ |
| Mauritanie      | M |
| Maurice       | MU |
| Mayotte         | YT |
| Mexique          | MX |
| Micronésie      | FM |
| Moldova         | MD |
| Monaco          | MC |
| Mongolie        | MN |
| Monténégro      | MOI |
| Montserrat      | MS |
| Maroc         | MA |
| Mozambique      | MZ |
| Myanmar         | MM |
| Namibie         | S.O. |
| Nauru           | NR |
| Népal           | NP |
| Pays-Bas     | NL |
| Nouvelle-Calédonie   | NC |
| Nouvelle-Zélande     | NZ |
| Nicaragua       | NI |
| Niger           | NE |
| Nigéria         | NG |
| Niue            | NU |
| Île Norfolk  | NF |
| Corée du Nord     | KP |
| Macédoine du Nord | MK |
| Îles Mariannes du Nord | NP |
| Norvège          | NON |
| Oman            | OM |
| Pakistan        | PK |
| Palaos           | PW |
| Autorité palestinienne | PS |
| Panama          | PA |
| Papouasie-nouvelle-guinée | PG |
| Paraguay        | PY |
| Pérou            | PE |
| Philippines     | PH |
| Pitcairn (îles) | PN |
| Pologne          | PL |
| Portugal        | PT |
| Porto Rico     | PR |
| Qatar           | QA |
| La Réunion         | RE |
| Roumanie         | RO |
| Russie          | RU |
| Rwanda          | RW |
| Saba            | XS |
| Saint Barthélemy | BL |
| Saint-Christophe-et-Niévès | KN |
| Sainte-Lucie     | LC |
| Saint Martin    | MF |
| Saint-Pierre-et-Miquelon | PM |
| Saint-Vincent-et-les-Grenadines | VC |
| Samoa           | WS |
| Saint-Marin      | SM |
| Sao Tomé-et-Principe | ST |
| Arabie Saoudite    | SA |
| Sénégal         | SN |
| Serbie          | RS |
| Seychelles      | SC |
| Sierra Leone    | SL | 
| Singapour       | SG |
| Saint-Eustache  | XE |
| Saint-Martin    | SX |
| Slovaquie        | SK |
| Slovénie        | SL |
| Salomon | SB |
| Somalie         | AINSI |
| Afrique du Sud    | ZA |
| Géorgie du Sud et Îles Sandwich du Sud | GS |
| Soudan du Sud     | SS |
| Espagne           | ES |
| Sri Lanka       | LK |
| Sainte-Hélène, Ascension, Tristan da Cunha | SH |
| Soudan           | SD |
| Suriname        | SR |
| Svalbard        | SJ |
| Suède          | SE |
| Suisse     | CH |
| Syrie           | SY |
| Taïwan          | TW |
| Tadjikistan      | TJ |
| Tanzanie        | TZ |
| Thaïlande        | TH |
| Timor-Leste     | TL |
| Togo            | TG |
| Tokelau         | TK |
| Tonga           | À |
| Trinité-et-Tobago | TT |
| Tunisie         | AMT |
| Turquie          | TR |
| Turkménistan    | TM |
| Îles Turks-et-Caïques | TC |
| Tuvalu          | TV |
| Îles de l’extérieur des États-Unis | Messagerie unifiée |
| Îles Vierges américaines | VI |
| Ouganda          | UG |
| Ukraine         | UA |
| Émirats arabes unis | AE |
| Royaume-Uni  | GB |
| États-Unis   | NOUS |
| Uruguay         | UY |
| Ouzbékistan      | UZ |
| Vanuatu         | VU |
| Vatican    | VA |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis-et-Futuna | WF |
| Yémen           | VOUS |
| Zambie          | ZM |
| Zimbabwe        | ZW |
