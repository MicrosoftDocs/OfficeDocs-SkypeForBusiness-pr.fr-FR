---
title: Indicatif pays de routage direct
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
description: Lisez cet article pour rechercher des codes de pays de chemin d’accès multimédia pour le routage direct et sélectionner la trajectoire de média optimale.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69265e797b256186f714e2cd4dcefcb3751c05ee
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904806"
---
# <a name="direct-routing-media-path-country-codes"></a>Itinéraires directs du pays

Lors du choix d’un chemin d’accès de routage pour le média, le routage directe par défaut affecte toujours un centre de contenus en fonction de l’adresse IP publique du contrôleur de bordure de session (SBC) et sélectionne toujours le chemin le plus proche du centre de médias SBC.

Toutefois, dans certains cas, il est possible que le chemin multimédia par défaut ne soit pas le chemin optimal pour le média. par exemple, une adresse IP publique d’une plage américaine peut être affectée à une SBC située en Europe. 

À l’aide du paramètre-MediaRelayRoutingLocationOverride avec les applets de requête New-CsOnlinePSTNGateway et Set-CsOnlinePSTNGateway, vous pouvez spécifier la région préférée pour le trafic multimédia. Par exemple, la commande suivante spécifie que la région préférée est Allemagne :

Set-CSOnlinePSTNGateway-Identity sbc1.contoso.com – MediaRelayRoutingLocationOverride DE 

Notez que Microsoft recommande uniquement de définir ce paramètre si les journaux d’appels indiquent clairement que l’affectation par défaut du centre de médias pour le chemin d’accès multimédia n’utilise pas le chemin le plus proche du centre de média SBC. 
 
## <a name="country-code-reference-table"></a>Tableau de référence de code pays

Le tableau suivant indique les valeurs de code de pays pour le paramètre-MediaRelayRoutingLocationOverride :

| Pays         | Codage 
|-----------------|--------------------|
| Afghanistan     | AF |
| Îles Alanes   | AX100 |
| Albanie         | & |
| Algérie         | DZ |
| Samoa américaines  | PLUS |
| Andorre         | AD |
| Angola          | AO |
| Anguilla        | Aï |
| Antarctique      | CAPTURE | 
| Antigua-et-Barbuda | GA |
| Argentine       | AR |
| Arménie         | 16H00 |
| Aruba           | AW |
| Australie       | AU |
| Autriche         | DÈS |
| Azerbaïdjan      | AZ |
| Bahamas         | BS |
| Bahreïn         | STATU |
| Bangladesh      | Ray |
| Barbade        | CONSTRUCTION |
| Bélarus         | BY |
| Belgique         | BE |
| Belize          | BZ |
| Bénin           | BJ |
| Bermudes         | BM |
| Bhoutan          | BT |
| Bolivie         | OÎTE |
| Bonaire         | BQ |
| Bosnie-Herzégovine | BA |
| Botswana        | POIDS |
| Île Bouvet   | BV |
| Brésil          | BR |
| Territoires britanniques de l’océan Indien | IO |
| Iles Vierges britanniques | VG |
| Brunei          | BN |
| Bulgarie        | BG |
| Burkina Faso    | BF |
| Burundi         | MENSUEL |
| Cabo-Verde      | VC |
| Cambodge        | KH |
| Cameroun        | CM |
| Canada          | CA |
| Îles Cayman  | KY |
| République centrafricaine | FC |
| Tchad            | ÉQUIPEMENTS |
| Chili           | CL |
| Chine           | CN |
| Christmas (île) | CX |
| Cocos-Keeling (îles) | CP |
| Colombie        | CO |
| Comores         | ACCUEILLANT |
| Congo           | CG |
| Congo (RDC)     | CD |
| Îles Cook    | CK |
| Costa Rica      | DM |
| Côte d’Ivoire   | CI |
| Croatie         | HR |
| Cuba            | CU |
| Curaçao (         | ACTUELLE |
| Chypre          | CY |
| Czechia         | CZ |
| Danemark         | DK |
| Djibouti        | LECTEUR |
| Dominique        | GD |
| République dominicaine | ÊTES |
| Équateur         | EC |
| Égypte           | EG |
| Salvador     | POURCENTAGE |
| Guinée Équatoriale | GQ |
| Érythrée         | QU’er |
| Estonie         | EE |
| Eswatini        | SZ |
| Éthiopie        | COMPTABILITÉ |
| Malouines (îles) | ÉTRANGÈRE |
| Îles Féroé   | DE |
| Fidji            | FJ |
| Finlande         | FI |
| France          | FR |
| Guyane française   | GF |
| Polynésie française | PF |
| Territoires français du Sud | TF |
| Gabonaise           | GA |
| Gambie          | GÉNÉTIQUE |
| Géorgie         | GE |
| Allemagne         | DE |
| Ghana           | GH |
| Gibraltar       | GASTRO |
| Grèce          | GR |
| Groenland       | OpenGL |
| Grenade         | GD |
| Guadeloupe      | CÂBLES |
| Guam            | G |
| Guatemala       | GT |
| Guernesey        | GG |
| Guinée          | NC |
| Guinée-Bissau   | Université |
| Guyane          | GY |
| Haïti           | Salut |
| Heard et McDonald (îles) | HM |
| Honduras        | HN |
| Hong Kong (R.A.S)   | HK |
| Hongrie         | HU |
| Islande         | ASSOCIÉ |
| Inde           | COMPLÉMENTAIRE |
| Indonésie       | ID |
| Iran            | RÉCEPTEUR |
| Irak            | MODULES |
| Irlande         | IE |
| Île de Man     | MI |
| Israël          | IL |
| Italie           | NE |
| Jamaïque         | JM |
| Jan Mayen       | XJ |
| Japon           | JP |
| T          | Djé |
| Jordanie          | Patrice |
| Kazakhstan      | KZ |
| Kenya           | KE |
| Kiribati        | KI |
| Corée           | KR |
| Kosovo          | XK |
| Koweït          | KILOWATT |
| Kirghizstan      | MAXIMUM |
| Laos            | Kanna |
| Lettonie          | TENSION |
| Liban         | G |
| Lesotho         | ! |
| Libéria         | GD |
| Libye           | LY |
| Liechtenstein   | LI |
| Lituanie       | LT |
| Luxembourg      | LU |
| Macao (R.A.S.)       | MO |
| Madagascar      | MG |
| Malawi          | MW |
| Malaisie        | MY |
| Maldives        | VM |
| Mali            | ML |
| Malte           | COMPLÉMENTAIRE |
| Îles Marshall | MH |
| Martinique      | MQ |
| Mauritanie      | Monsieur |
| Maurice       | MU |
| Mayotte         | YT |
| Mexique          | MX |
| Micronésie      | FM |
| Moldova         | MD |
| Monaco          | MC |
| Mongolie        | PORTABLE |
| Monténégro      | RECEVOIR |
| Montserrat      | SM |
| Maroc         | TÉLÉPHONIQUE |
| Mozambique      | MZ |
| Myanmar         | HAUTEUR |
| Namibie         | S.O. |
| Nauru           | NR |
| Népal           | VERROU |
| Pays-Bas     | NL |
| Nouvelle-Calédonie   | NC |
| Nouvelle-Zélande     | EXAMINER |
| Nicaragua       | NICKEL |
| Niger           | NÉ |
| Nigéria         | GN |
| Niue            | NU |
| Île Norfolk  | G |
| Corée du Nord     | KP |
| Macédoine du Nord | MK |
| Îles Mariannes du Nord | VERROU |
| Norvège          | AUCUN |
| Oman            | OM |
| Pakistan        | PRIMAIRE |
| Palaos           | P |
| Autorité palestinienne | RECOURIR |
| Panama          | PA |
| Papouasie-Nouvelle-Guinée | PRÉC |
| Paraguay        | PY |
| Pérou            | PE |
| Philippines     | PH |
| Îles Pitcairn | PN+1 |
| Pologne          | PL |
| Portugal        | PT |
| Porto Rico     | PR |
| Qatar           | QA |
| La Réunion         | INSCRIRE |
| Roumanie         | RO |
| Russie          | Arabie |
| Rwanda          | INSÉRÉ |
| Saba            | REMPLACÉ |
| Saint-Barthelemy | BL |
| Saint-Christophe-et-Niévès | KN |
| Sainte-Lucie     | EUROS |
| Saint-Martin    | MF |
| Saint-Pierre-et-Miquelon | 18H |
| Saint-Vincent-et-les-Grenadines | VC |
| Hiver           | NOMBRES |
| Saint-Marin      | SM |
| Sao Tomé-et-principe | ÈRE |
| Arabie Saoudite    | SA |
| Sénégal         | SN |
| Serbie          | RS |
| Seychelles      | GAMME |
| Sierra Leone    | GRESSIF | 
| Singapour       | SG |
| Saint-Eustache  | CHAMP |
| Saint--Maarten    | SX |
| Slovaquie        | SK |
| Slovénie        | GRESSIF |
| Îles Salomon | Synth |
| Somalie         | AFIN |
| Afrique du Sud    | ZA |
| Géorgie du Sud-et-les îles Sandwich du Sud | GS |
| Soudan du Sud     | SÉCURITÉ |
| Espagne           | ES |
| Sri Lanka       | LK |
| Sainte-Hélène, ascension et Tristan da Cunha | & |
| Soudan           | ARCHITECTURE |
| Suriname        | TOUCHES SR |
| Svalbard        | SJ |
| Suède          | SE |
| Suisse     | CHAPITRE |
| Syrie           | SY |
| Taïwan          | TW |
| Tadjikistan      | TJ |
| Tanzanie        | TZ |
| Thaïlande        | TH |
| Timor-oriental     | TL |
| Togo            | DÉCRITE |
| Îles Tokelau         | TK |
| Tonga           | À |
| Trinité-et-Tobago | IT |
| Tunisie         | TN |
| Turquie          | TR |
| Turkménistan    | TRADUCTION |
| Turks et Caicos (îles) | TC |
| Îles Tuvalu          | TÉLÉVISEUR |
| Îles éloignées des États-Unis | UM |
| Iles Vierges américaines | VI |
| Ouganda          | G |
| Ukraine         | AGENT |
| Émirats arabes unis | AE |
| Royaume-Uni  | GB |
| États-Unis   | Nous |
| Uruguay         | UY |
| Ouzbékistan      | UZ |
| Vanuatu         | VOU |
| Vatican    | V |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis-et-Futuna | WF |
| Yémen           | Yé |
| Zambie          | ZM |
| Zimbabwe        | ZW |

