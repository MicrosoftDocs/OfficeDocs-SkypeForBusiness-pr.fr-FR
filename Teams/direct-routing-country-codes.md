---
title: Codes de pays de routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lisez cet article pour identifier les codes de pays de chemin de médias pour le routage direct afin de sélectionner le chemin de médias optimal.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69265e797b256186f714e2cd4dcefcb3751c05ee
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904806"
---
# <a name="direct-routing-media-path-country-codes"></a>Direct Routing media path country codes

Lorsque vous choisissez un itinéraire de routage pour le média, le routage direct affecte toujours par défaut un centre de données basé sur l’adresse IP publique du contrôleur de session en bordure (SBC), et sélectionne toujours le chemin le plus proche du centre de données SBC.

Toutefois, dans certains cas, le chemin de médias par défaut peut ne pas être le chemin multimédia optimal . Par exemple, une adresse IP publique provenant d’une plage aux États-Unis peut être affectée à unbc SBC situé en Europe. 

En utilisant le paramètre -MediaRelayRoutingLocationOverride avec les cmdlets New-CsOnlinePSTNGateway et Set-CsOnlinePSTNGateway>, vous pouvez spécifier la région préférée pour le trafic de médias. Par exemple, la commande suivante indique que la région préférée est Allemagne :

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Notez que Microsoft recommande de définir ce paramètre uniquement si les journaux d’appels indiquent clairement que l’affectation par défaut du centre de données pour le chemin de médias n’utilise pas le chemin le plus proche du centre de données SBC. 
 
## <a name="country-code-reference-table"></a>Table de référence des codes de pays

Le tableau suivant indique les valeurs de code de pays pour le paramètre -MediaRelayRoutingLocationOverride :

| Pays         | Code 
|-----------------|--------------------|
| Afghanistan     | AF |
| Îles Aland   | AX |
| Albanie         | AL |
| Algérie         | DZ |
| Samoa américaines  | AS |
| Andorre         | AD |
| Angola          | AO |
| Anguilla        | AI |
| Antarctique      | AQ | 
| Antigua-et-Barbuda | INSER |
| Argentine       | AR |
| Arménie         | AM |
| Aruba           | AW |
| Australie       | AU |
| Autriche         | AT |
| Azerbaïdjan      | AZ |
| Bahamas         | BS |
| Bahreïn         | SO |
| Bangladesh      | BD |
| Barbade        | BB |
| Bélarus         | BY |
| Belgique         | BE |
| Belize          | BZ |
| Bénin           | BJ |
| Bermudes         | MBY |
| Bhoutan          | BT |
| Bolivie         | BO |
| Bonaire         | BQ |
| Bosnie-Herzégovine | BA |
| Botswana        | NB |
| Île Bouland   | BV |
| Brésil          | BR |
| Territoire britannique de l’océan Indien | IO |
| Îles Vierges britanniques | VG |
| Brunei          | BN |
| Bulgarie        | BG |
| Burkina Faso    | BF |
| Burundi         | BI |
| Cabo Verde      | VC |
| Cambodge        | KH |
| Cameroun        | CM |
| Canada          | CA |
| Îles Cayman  | KY |
| République centrafricaine | CF |
| Tchad            | TD |
| Chili           | CL |
| Chine           | CN |
| Île Christmas | CX |
| Îles Cocos | CC |
| Colombie        | CO |
| Comores         | KM |
| Congo           | CG |
| Congo (RDC)     | CD |
| Îles Cook    | CK |
| Costa Rica      | CR |
| Côte d’Ivoire   | CI |
| Croatie         | HR |
| Cuba            | CU |
| Curaçao         | CW |
| Chypre          | CY |
| République tchèque         | CZ |
| Danemark         | DK |
| Djibouti        | Z |
| Dominique        | DM |
| République dominicaine | DO |
| Équateur         | EC |
| Égypte           | EG |
| Salvador     | SV |
| Guinée Équatoriale | GQ |
| Érythrée         | ER |
| Estonie         | EE |
| Eswa qu’on ne peut pas faire        | SZ |
| Éthiopie        | ET |
| Malouines (îles) | FK |
| Îles Féroé   | FO |
| Fidji            | FJ |
| Finlande         | FI |
| France          | FR |
| Guyane française   | GF |
| Polynésie française | PF |
| Terres australes françaises | TF |
| Gabon           | GA |
| Gambie          | GM |
| Géorgie         | GE |
| Allemagne         | DE |
| Ghana           | GAND |
| Gibraltar       | GI |
| Grèce          | GR |
| Groenland       | GL |
| Grenade         | GD |
| Guadeloupe      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | GG |
| Guinée          | GN |
| Guinea-Bissau   | GW |
| Guyane          | GY |
| Haïti           | Salut |
| Heard et McDonald (îles) | HM |
| Honduras        | HN |
| Hong Kong (R.A.S)   | HK |
| Hongrie         | HU |
| Islande         | EST |
| Inde           | IN |
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
| Kersti        | KI |
| Corée           | KR |
| Monde          | XK |
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
| Macao (R.A.S.       | MO |
| Madagascar      | Z |
| Malawi          | Z |
| Malaisie        | MY |
| Maldives        | MV |
| Mali            | ML |
| Malte           | MT |
| Îles Marshall | MH |
| Martinique      | MQ |
| Algérie      | MR |
| Maurice       | MU |
| Mayotte         | YT |
| Mexique          | MX |
| Micronésie      | FM |
| Moldova         | MD |
| Monaco          | MC |
| Mongolie        | MN |
| Monténégro      | ME |
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
| ÎleSQuel  | NF |
| Corée du Nord     | KP |
| Macédoine du Nord | MK |
| Îles Mariannes du Nord | NP |
| Norvège          | NO |
| Oman            | OM |
| Pakistan        | PK |
| Palaos           | PW |
| Autorité palestinienne | PS |
| Panama          | PA |
| Papouasie-Nouvelle-Guinée | PG |
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
| SaintSélecmy | BL |
| Saint-Christophe-et-Niévès | KN |
| Sainte-Lucie     | LC |
| Saint Martin    | PPXT |
| Saint-Pierre-et-Miquelon | PM |
| Saint-Vincent-et-les-Grenadines | VC |
| Samoa           | WS |
| Saint-Marin      | SM |
| São Tome et Principe | ST |
| Arabie Saoudite    | SA |
| Sénégal         | SN |
| Serbie          | RS |
| Seychelles      | SC |
| Sierra Leone    | SL | 
| Singapour       | SG |
| Sint Eustatius  | XE |
| Saint-Maarten    | SX |
| Slovaquie        | SK |
| Slovénie        | SL |
| Îles Islands | SB |
| Somalie         | SO |
| Afrique du Sud    | ZA |
| Géorgie du Sud et îles Sandwich du Sud | GS |
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
| Tunisie         | TN |
| Turquie          | TR |
| Turkménistan    | TM |
| Turks et Caicos (îles) | TC |
| Tuvalu          | Téléviseur |
| Îles sortantes des États-Unis | UM |
| Îles Vierges des États-Unis | VI |
| Ouganda          | UG |
| Ukraine         | UA |
| Émirats arabes unis | AE |
| Royaume-Uni  | GB |
| États-Unis   | États-Unis |
| Uruguay         | UY |
| Ouzbékistan      | UZ |
| Vanuatu         | VU |
| Cité du Vatican    | VA |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis-et-Futuna | WF |
| Yémen           | YE |
| Zambie          | ZM |
| Zimbabwe        | SYSTÈME D’ÉQUIPES |

