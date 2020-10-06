---
title: Application patients et interface DSTU2 d’intégration DMI
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
description: Apprenez-en davantage sur la spécification de l’interface DSTU2 dans Teams, notamment la configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2fa5575d6d7a4cbdffec6c3396004c38e743720a
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361454"
---
# <a name="dstu2-interface-specification"></a>Spécification de l’interface DSTU2

> [!IMPORTANT]
> **À compter du 15 octobre 2020, l’application patients sera déconseillée et les utilisateurs ne pourront plus l’installer à partir de l’App Store d’Teams. Nous vous encourageons à commencer à utiliser l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans teams dès aujourd’hui.**
>
>Les données d’application patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui fait reculer l’équipe. Lorsque l’application patients est supprimée, toutes les données qui lui sont associées seront conservées dans ce groupe, mais ne seront plus accessibles par le biais de l’interface utilisateur. Les utilisateurs actuels peuvent recréer leurs listes à l’aide de l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>L' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) est préinstallée pour tous les utilisateurs d’teams et est disponible sous la forme d’une tabulation dans chaque équipe ou canal. Les listes permettent aux équipes de soins de créer des listes de patients à l’aide du modèle de patients intégré, de zéro à partir de zéro ou d’importer des données dans Excel. Pour en savoir plus sur la gestion de l’application listes au sein de votre organisation, voir [gérer l’application listes](../../manage-lists-app.md).

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La configuration ou la reconfiguration d’un serveur FHIR pour l’utilisation de l’application Microsoft teams patients nécessite une compréhension des données auxquelles l’application doit accéder. Le serveur FHIR doit prendre en charge les demandes POST à l’aide de bottes pour les ressources suivantes :

- [Patient](#patient)
- [Déterminée](#observation)
- [Condition](#condition)
- [Connaître](#encounter)
- [Intolérance des allergies](#allergyintolerance)
- [Articles](#coverage)
- [Ordre de médication](#medication-order)
- [Emplacement](#location)

> [!NOTE]
> La ressource patient est la seule ressource obligatoire (sans que l’application ne se charge du tout. Néanmoins, nous vous conseillons de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus pour une utilisation optimale de l’application Microsoft teams pour les utilisateurs finaux.

Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources ont une offre groupée (lot) de requêtes à l’URL du serveur FHIR. Le serveur traite chaque demande et renvoie un ensemble de ressources correspondant à chaque demande. Pour plus d’informations et d’exemples, voir [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) .

Toutes les ressources FHIR suivantes doivent être accessibles par référence directe aux ressources.

## <a name="conformance-minimum-required-field-set"></a>Jeu de champs requis de conformité

 Le serveur FHIR doit mettre en œuvre la déclaration de conformité afin d’avoir une synthèse factuelle de ses capacités. Nous attendons les paramètres ci-dessous dans un DSTU2 FHIR Server :

1. LAISSER
   1. Veille
   2. Interaction
   3. Ressource : type
   4. Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (notre code nécessite une telle mesure pour savoir quelle version nous devons faire pivoter à mesure que nous prenons en charge plusieurs versions.)

[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="patient"></a>Patient

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du [Profil du patient Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

1. Name. Family
2. Nom. fourni
3. Public
4. Anniversaire
5. NRM (identificateur)

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :

1. Name. use
2. Nom. préfixe
3. CareProvider (cette référence sur la ressource patient doit inclure les champs d’affichage illustrés dans l’exemple suivant.)

* * *

    Demande : obtenez <fhir-Server>/patient/<patient-ID>
    
    Réponse : {"resourceType" : "patient", "ID" : "<patient-ID>",.
      .
      .
      "nom" : [{"utilisation" : "officiel", "préfixe" : ["Mr"], "famille" : ["Chau"], "en"; ";" ";" ";" ";" officiel "," tapez " : {" codage " : [{" système " :" https://hl7.org/fhir/v2/0203 "," code " :" 1234567 "}])," valeur " :" "}]," sexe "," careProvider "," DateNaissance " :" 1957-06-05 "," " : [{" Display " :" Jane Dupont "}],}

* * *

Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :

1. ID
2. famille : contient = (recherche les patients dont le nom de famille contient la valeur.)
3. accordé =\<substring>
4. Name =\<substring>
5. DateNaissance = (correspondance exacte)
6. \_nombre (nombre maximal de résultats à renvoyer) <br> La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche, et \_ le nombre sera utilisé par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.
7. identificateur =\<mrn>

L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :

- ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.
- NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait. Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR
- Nom
- Anniversaire

Pour plus d’informations, reportez-vous à l’exemple suivant.

* * *

    Request : POST <fhir-Server>/patient/_search corps de la requête : fourni = Hugh&Family = Chau
    
    Réponse : {"resourceType" : "bundle", "ID" : "<-ID>",.
      .
      .
      "entrée" : [{"ressource" : {"resourceType" : "patient", "ID" : "ID patient-ID>", "nom" : [{"texte" : "Hugh Chau", "<famille" : [Chau "]," nom " : [" Hugh "]}]," sexe " :" mâle "," DateNaissance " :" 1957-06-05 "}," recherche " : {" mode " :" match "}})}

* * *

[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="observation"></a>Déterminée

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil de signes vitaux de Argonaut :

 1. Effective (heure de date ou période)
 2. Code. Coding. code
 3. ValueQuantity. Value

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :

 1. Code. Coding. Display
 2. ValueQuantity. Unit

S’il s’agit d’une observation de composant, la même logique s’applique à chaque composant d’observation.

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<patient id\>
2. Trier : DESC =\<field ex. date\>

L’objectif est de pouvoir récupérer les derniers signes vitaux pour un patient, [VitalSigns. DSTU. saz] (observation ?).

* * *

    Demande : obtenez <fhir-Server>/observation ? patient =<patient-ID>&_sort :d Échap = date&catégorie = vitaux-signes
    
    Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "tapez" : "searchset", "total" : 20, "entrée" : [{"ressource" : {"resourceType" : "observation", "ID" : "<-id de ressource", "category" : {"code" : {{code " :" "Pseudo"> = "" code " : {" codage " : [{" système " :" http://loinc.org "," code " :" 39156-5 "," Display " :" BMI "}),}," effectiveDateTime " :" 2009-12-01 "," valueQuantity " : {" value " : 34,4," Unit " :" kg/m2 "," système " :" http://unitsofmeasure.org "," code " :" kg/m2 "}},},.
        .
        .
      ] }

* * *

[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="condition"></a>Condition

Il s’agit des champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code. Coding [0]. 3D

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

1. Date d’enregistrement
2. Minimal

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<patient id>
2. _count =\<max results>

Pour plus d’informations, reportez-vous à l’exemple suivant :

* * *

    Demande : obtenez <fhir-Server>/condition ? patient =<patient-ID>&_count = 10
    
    Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type", "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "condition", "ID" : "<-ID>", "code" : {"Coding" : [{"System" : " http://snomed.info/sct ", "code" : "386033004", "Display" : "neuropathie (dommage nerveux)"}]}, "dateRecorded" : "2018-09-17", "gravité" : {"codage" : [{"système" : " http://snomed.info/sct ", "code" : "24484000", "Display" : "sévère"}]}}})}

* * *

[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="encounter"></a>Connaître

Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs du profil de rencontre du cœur américain « doivent avoir » des champs :

1. État
2. Tapez [0]. Code [0]. 3D

De plus, les champs suivants provenant des champs du profil « doit prendre en charge » sont les suivants :

1. Période. début
2. Emplacement [0]. Emplacement. Display

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<patient id>
2. _sort : DESC =\<field ex. date>
3. _count =\<max results>

L’objectif est de pouvoir récupérer le dernier emplacement connu du patient. Chaque rencontre fait référence à une ressource d’emplacement. La référence inclut également le champ d’affichage de l’emplacement. Pour plus d’informations, reportez-vous à l’exemple suivant.
* * *

    Demande : obtenez <fhir-Server>/Encounter ? patient =<patient-ID>&_sort :d Échap = date&_count = 1
    
    Réponse : {"resourceType" : "bundle", "type", "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "rencontre", "identifiant" : "<-ID>", "identificateur" : [{"utiliser" : "officiel", "valeur" <id> Status " :" incomplet "," type " : [{" Coding " : [{" Display " :" rendez-vous "}],})," patient " : {" Réf "<>"}, "période" : {"début" : "09/17/2018 1:00:00 PM"}; "lieu" : [{"lieu" : {"Display" : "Clinic-ent"}})}

* * *

[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="allergyintolerance"></a>AllergyIntolerance

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut AllergyIntolerance :

1. Code. Text
2. Code. Coding [0]. 3D
3. État

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :

1. RecordedDate
2. Remarque. Text
3. Réaction [...]. Substance. texte
4. Réaction [...]. Manifeste [...]. Synthèse
5. Text. div

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. Patient =  \<patient id>

Pour plus d’informations, reportez-vous à l’exemple suivant :

* * *

    Demande : obtenez <fhir-Server>/AllergyIntolerance ? patient =<patient-ID>
    
    Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type", "searchset", "total" : 1, "entry" : "AllergyIntolerance", "ID" : "<-ID>", "recordedDate" : "" 2018-09-17T07:00:00.000 Z "," substance " : {" texte " :" Cashew écrous "}," statut " :" confirmé "," réaction " : [{" substance " : {" texte " :" Cashew d’écrou d’écrou allergique "}," manifeste " : [{" texte " :" anaphylactic réaction "}]}]}}]}

* * *

[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="medication-order"></a>Ordre de médication

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut MedicationOrder :

1. DateWritten
2. Ordonnateur. Display
3. Médication. Display (Si référence)
4. Medication. Text (si concept)

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

1. DateEnded
2. DosageInstruction. Text
3. Text. div

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<patient id>
2. _count =\<max results>

Pour plus d’informations, reportez-vous à l’exemple suivant :

* * *

    Demande : obtenez <fhir-Server>/MedicationOrder ? patient =<patient-ID>&_count = 10
    
    Réponse : {"resourceType" : "bundle", "ID" : "<-ID>", "type" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "MedicationOrder", "ID" : "<-ID de ressource>", "dateWritten" : "2018-09-17", "medicationCodeableConcept" : {"Text" : "Lisinopril 20 MG de comprimé"}, "" : "Jane Dupont"}, "dosageInstruction" : [{"Text" : "1 quotidien"}

* * *  

[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="coverage"></a>Articles

Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :

1. Payor

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<patient id>

Pour plus d’informations, reportez-vous à l’exemple suivant :

* * *

    Demande : obtenez <fhir-Server>/Coverage ? patient =<patient-ID>
    
    Réponse : {"resourceType" : "bundle", "tapez" : "searchset", "total" : 1, "entrée" : [{"ressource" : {"resourceType" : "couverture", "ID" : "<-id de ressource", "plan" : "pas d'> assurance primaire", "abonné" : {"référence" : "patient/<patient-ID>"}}}]}

* * *

[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="location"></a>Lieu

Cette ressource est uniquement utilisée comme référence sur la ressource de [rencontre](#encounter) .

[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Pour plus d’informations sur ce jeu de champs, voir.
