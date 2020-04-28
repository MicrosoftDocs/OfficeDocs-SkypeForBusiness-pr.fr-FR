---
title: Application patients et interface STU3 d’intégration DMI
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: En savoir plus sur l’intégration d’enregistrements de santé électronique dans l’application Microsoft teams patients et la spécification de l’interface STU3.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2e101f6ca50a76b4b8bb9d3dd33d35fd7706a81f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905746"
---
# <a name="stu3-interface-specification"></a>Spécification de l’interface STU3

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients nécessite une compréhension des données auxquelles l’application doit accéder. Le serveur FHIR doit prendre en charge les demandes POST à l’aide de bottes pour les ressources suivantes :

- [Patient](#patient)
- [Déterminée](#observation)
- [Condition](#condition)
- [Connaître](#encounter)
- [Intolérance des allergies](#allergyintolerance)
- [Articles](#coverage)
- [État de médication](#medication-request) (remplace le MedicationOrder dans la version DSTU2 du PatientsApp)
- Emplacement (les informations requises par cette ressource peuvent être intégrées à la rencontre)

> [!NOTE]
> La ressource patient est la seule ressource obligatoire (sans que l’application ne se charge du tout); Néanmoins, nous vous conseillons de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus pour une utilisation optimale de l’application Microsoft teams pour les utilisateurs finaux.

Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources publient une offre (BATCH) de requêtes dans l’URL du serveur FHIR. Le serveur traitera chaque demande et renverra une offre de ressources correspondant à chaque demande. Pour plus d’informations et d’exemples [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction), voir.

## <a name="capability-statement"></a>Instruction Capability

Voici les champs obligatoires obligatoires :

1. LAISSER
   1. Veille
   2. Interaction
   3. Ressource : type
   4. Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (notre code nécessite cela pour comprendre la version à laquelle nous devons faire pivoter.)

Pour [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) plus d’informations sur ce jeu de champs, voir.

## <a name="patient"></a>Patient

Voici les champs requis au minimum, qui sont un sous-ensemble des champs du profil du patient Argonaut :

1. Nom. fourni
2. Name. Family
3. Public
4. Anniversaire
5. NRM (identificateur)

Outre les [champs Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

1. Name. use
2. Nom. préfixe
3. [GeneralPractitioner] : la référence GeneralPractitioner doit être incluse dans la ressource patient (champ d’affichage uniquement)

Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :

1. ID
2. famille = (recherche tous les patients dont le nom de famille contient la valeur)
3. fourni =\<sous-chaîne>
4. DateNaissance = (correspondance exacte)
5. sexe = (valeurs faisant partie d’un compte d’administrateur-sexe)
6. \_nombre (nombre maximal de résultats à renvoyer) <br> La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche et \_du comptage qui seront utilisés par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.
7. identifiant =\<NRM>

L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :

- ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.
- NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait. Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR.
- Nom
- Anniversaire

Pour plus d’informations, reportez-vous à l’exemple suivant :

* * *

    Request : POST <fhir-Server>/patient/_search corps de la requête : fourni = Ruth&Family = Black
    
    Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "meta" : {"lastUpdated" : "2019-01-14T23:44:45.052 + 00:00"}, "tapez" : "searchset", "total" : 1, "Self", "URL" : « auto », « URL » : <fhir-Server>/patient/_search "}]," entrée " : [{" fullUrl " : <fhir-Server>/patient/<patient-ID>", "ressource" : {"resourceType" : "patient", "ID" : "<patient-ID>", "meta" : {"versionId" : "1", "lastUpdated" : "2017-10-18T18:32:37.000 + 00:00"}, "texte" : {"Status" : "generated", "div" : "<div>\n        <p>Noir Ruth</p>\n      </div>"}," identificateur " : [{" use " :" usuelle "," type " : {" codification " : [{" System " :"https://hl7.org/fhir/v2/0203"," code " :" Mr "," Display "," "userSelected" : false}], "texte" : "http://hospital.smarthealthit.org", "", "", "", "", "valeur" : "1234567"}], "actif" : vrai, "nom" : "" ";" ""; ""; ""; "" ";"
    ]}], "Telecom" : [{"système" : "téléphone", "valeur" : "800-599-2739", "utiliser" : "maison"}, {"système" : "téléphone", "valeur" : "800-808-7785", "utiliser" : "mobile"}, {"système" : "ruth.black@example.com" = "" valeur "femelle", "DateNaissance" : "1951-08-23", "adresse" : [{"utiliser" : "maison", "ligne" : ["26 South RdApt 22"], "ville" : "sapâtea", "État" : "OK", "CodePostal" : "74066", "Country" : "USA"}]), "Search" : {"mode" : "match"}})}

* * *

    Demande : obtenez <fhir-Server>/patient/<patient-ID>
    
    Réponse : {"resourceType" : "patient", "ID" : "<patient-ID>", "identificateur" : [{"use" : "usuelle", "type" : {"codage" : [{"système" : "https://hl7.org/fhir/v2/0203", "code" : "Mr",}], "texte" : "le numéro de l’enregistrement médical"}, "valeur" : "1234567"}], "nom" : [{"utiliser" : "officiel", "famille" : "Adams", ""» : "Michel", "X." ]}], "sexe" : "mâle", "DateNaissance" : "1925-12-23",}

* * *

Pour [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) plus d’informations sur ce jeu de champs, voir.

## <a name="observation"></a>Déterminée

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du [profil de signes vitaux de Argonaut](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

1. Effective (heure de date ou période)
2. Code. Coding. code
3. ValueQuantity. Value

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

1. Code. Coding. Display
2. ValueQuantity. Unit

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<ID du patient>
2. _sort = date
3. Category (nous interrogerons « Category = vitaux-Sign-signes ») pour récupérer la liste des signes vitaux.

Reportez-vous à cet exemple de l’appel :

* * *

    Demande : obtenez <fhir-Server>/observation ? patient =<patient-ID>&catégorie = vitaux-signes
    
    Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 20, "entrée" : [{"ressource" : {"resourceType" : "observation", "ID" : "<-ID>", "category" : [{"code" : [{"System", "https://hl7.org/fhir/observation-category", "code" : "" code " : {" Coding " : [{" System " :"http://loinc.org"," code " :" 8867-4 "," display " :" heart_rate "}]}," effectiveDateTime " :" 2009-04-08T00:00:00-06:00 "," valueQuantity " : {" value " : 72,0," Unit " :" {temps} minute "," système " :"http://unitsofmeasure.org",}}},.
        .
        .
      ] }

* * *

Pour [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) plus d’informations sur ce jeu de champs, voir.

## <a name="condition"></a>Condition

Voici les champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

1. Code. Coding [0]. 3D

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

1. AssertedDate
2. Minimal

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<ID du patient>
2. _count =\<résultats maximum>

Pour plus d’informations, reportez-vous à l’exemple suivant :

* * *

    Demande : obtenez <fhir-Server>/condition ? patient =<patient-ID>&_count = 10
    
    Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type", "searchset", "total" : 2, "entry" : [{"Resource" : {"resourceType" = "condition", "ID" : "<-ID>", "code" : {"code"http://snomed.info/sct"," code " :" 185903001 "," Display " :" nécessite une immunisation de la grippe ",}]}," gravité " : {" codage " : [{" System " :"http://snomed.info/sct"," code " :" 24484000 "," Display " :" assertedDate "}}," " :" 2018-04-04 "}};
        .
        .
      ] }

* * *
Pour [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) plus d’informations sur ce jeu de champs, voir.

## <a name="encounter"></a>Connaître

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du profil de type [rencontrent des États-Unis](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .

1. État
2. Tapez [0]. Code [0]. 3D

De plus, les champs suivants provenant du cœur Microsoft pour les États-Unis du profil « doivent prendre en charge » :

1. Période. début
2. Emplacement [0]. Emplacement. Display

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<ID du patient>
2. _sort : DESC =\<champ ex. Date>
3. _count =\<résultats maximum>

L’objectif est de pouvoir récupérer le dernier emplacement connu du patient. Chaque rencontre fait référence à une ressource d’emplacement. La référence inclut également le champ d’affichage de l’emplacement.

Pour [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) plus d’informations sur ce jeu de champs, voir.

## <a name="allergyintolerance"></a>AllergyIntolerance

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

1. Code. Text
2. Code. Coding [0]. 3D
3. ClinicalStatus/VerificationStatus (nous avons lu les deux)

Outre les champs Argonaut, pour optimiser l’utilisation de l’application patients, l’application patients peut également lire le champ suivant :

1. AssertedDate
2. Remarque. Text
3. Réaction
    1. Substance (un élément de codage)
    2. Manifeste (un élément de codage)

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. Patient = \<ID du patient>

Pour plus d’informations, reportez-vous à l’exemple suivant : 

* * *

    Demande : obtenez <fhir-Server>/AllergyIntolerance ? patient =<patient-ID>
    
    Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType", "AllergyIntolerance", "ID" : "<-ID>", "clinicalStatus" : "actif", "verificationStatus" : "confirmé", "code" : {"http://rxnav.nlm.nih.gov/REST/Ndfrtcode" : "", "code" : "N0000175503", "Display" : "sulfonamide antibactérienne",}], "texte" : "sulfonamide antibactérienne"}, "assertedDate" : "2018-01-01T00:00:00-07:00", "réaction" : [{"se manifester" : [{"codage" : [{"système" : "http://snomed.info/sct", "code" : "271807003", "Display" : "Skin rash",}), "Text" : "Skin rash"}]

* * *

Pour [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) plus d’informations sur ce jeu de champs, voir.

## <a name="medication-request"></a>Demande de médication

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du [profil de demande de médicament principal pour les États-Unis](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

1. Médication. Display (Si référence)
2. Médication. Text (si CodableConcept)
3. AuthoredOn
4. Demandeur. agent. Display

Outre les champs de base américaine, l’application patients peut également lire les champs suivants pour une utilisation optimale :

1. DosageInstruction[..]. Synthèse
2. Synthèse

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<ID du patient>
2. _count =\<résultats maximum>

Pour [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) plus d’informations sur ce jeu de champs, voir.

## <a name="coverage"></a>Articles

Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :

1. Regroupement d’au moins un élément avec
    1. GroupDisplay
    2. PlanDisplay
2. Donnée
3. SubscriberId

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. Patient = \<ID du patient>

Pour [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) plus d’informations sur ce jeu de champs, voir.
