---
title: Application des patients et DMP interface d’intégration STU3
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Intégration de Patients d’équipes Microsoft app DMI
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643095"
---
# <a name="stu3-interface-specification"></a>Spécification d’interface STU3

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Configuration ou la reconfiguration d’un serveur FHIR pour fonctionner avec l’application Microsoft équipes Patients, vous devez comprendre les données de l’application doit accéder. Le serveur FHIR doit prendre en charge les demandes POST à l’aide de groupes pour les ressources suivantes :

- [Patient](#patient)
- [Observation](#observation)
- [Condition](#condition)
- [Rencontrez](#encounter)
- [INTOLÉRANCE allergies](#allergyintolerance)
- [Couverture](#coverage)
- [Instruction MEDICATION](#medication-request) (remplace la MedicationOrder dans la version DSTU2 de le PatientsApp)
- Emplacement (les informations nécessaires à partir de cette ressource peut être incluses dans rencontre)

> [!NOTE]
> La ressource Patient est la ressource obligatoire uniquement (sans laquelle l’application chargera pas du tout) ; Toutefois, il est recommandé que le partenaire de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus par les spécifications indiquées ci-dessous pour la meilleure expérience utilisateur final avec l’application de Patients équipes Microsoft.

Requêtes à partir de l’application Microsoft équipes Patients pour plusieurs ressources doivent publier un lot (BATCH) des demandes à l’URL du serveur FHIR. Le serveur doit traiter chaque demande et renvoyer un ensemble de ressources correspondant à chaque demande. Pour plus d’informations et des exemples, voir [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).

## <a name="capability-statement"></a>Instruction de fonctionnalité

Voici les champs obligatoires minimales :

1. REST
   1. Mode
   2. Interaction
   3. Ressource : Type
   4. Sécurité : [Extension pour les URI OAuth](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (notre code requiert cette option pour comprendre de quelle version nous devons de tableau croisé dynamique à).

Voir [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) pour plus de détails sur ce champ défini.

## <a name="patient"></a>Patient

Voici les champs obligatoires minimales, qui sont un sous-ensemble des champs profil patients Argonaut :

1. Name.Given
2. Name.Family
3. Sexe
4. Date de naissance
5. NRM (identificateur)

Outre les [champs Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :

1. Name.Use
2. Name.Prefix
3. [GeneralPractitioner] - GeneralPractitioner la référence doit être inclus dans la ressource Patient (champ Affichage uniquement)

Une recherche de ressource utilise la méthode POST /Patient/_search et les paramètres suivants :

1. ID
2. famille = (tous les patients dont le nom de famille contient la valeur de la recherche)
3. donnée =\<substring>
4. date de naissance =(exact match)
5. sexe = (valeurs dont le sexe-administration)
6. \_Count (nombre maximal de résultats qui doit être retourné) <br> La réponse doit contenir le nombre total d’enregistrements renvoyés à la suite de la recherche et \_count utilisera le PatientsApp pour limiter le nombre d’enregistrements renvoyés.
7. identificateur =\<mrn>

L’objectif doit être en mesure de recherche et filtrage d’un patient par les éléments suivants :

- ID : Il s’agit de l’ID de ressource a toutes les ressources de FHIR.
- NRM : Il s’agit de l’identificateur pour le patient personnel savez réel. Nous savons que ce NRM est basé sur le type d’identificateur à l’intérieur de la ressource de l’identificateur dans FHIR.
- Nom
- Date de naissance

Consultez l’exemple de l’appel suivant :

* * *

    Requête : Corps de la demande POST <fhir-server>/Patient/_search : donnée = ruth&family = noir
    
    Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « meta » : {« lastUpdated » : « 2019-01-14T23:44:45.052 + 00:00 »}, « type » : « searchset », « total » : 1, « lien » : [{« relation » : « self », « url » : <fhir-server>/Patient/_search »}], « entry » : [{ « fullUrl » : <fhir-server>/Patient/<patient-id> », « ressource » : {« resourceType » : « Patient », « id » : « <patient-id> », « meta » : {« versionId » : « 1 », « lastUpdated » : « 2017-10-18T18:32:37.000 + 00:00 »}, « texte » : {« status » : « généré », « div ": "<div>\n        <p>Roland noir</p>\n      </div>«}, « identificateur » : [{« utiliser » : « normal », « type » : {« codage » : [{« système » : «http://hl7.org/fhir/v2/0203», « code » : « MR », « afficher » : « numéro de dossier médical », « userSelected » : false}], « texte » : « numéro de dossier médical »}, « système » : «http://hospital.smarthealthit.org», « valeur » : « 1234567 »}], « actif » : true, » « nom : [{« utiliser » : « officielle », « famille » : « Noir », « attribué » : [« Michael Jordan » « c ».
    ]}], « télécommunications » : [{« système » : « téléphoniques », « valeur » : utilisation » « 800-599-2739 », » : « d’accueil »}, {« système » : « téléphoniques », « valeur » : utilisation » « 800-808-7785 », » : « mobile »}, {« système » : « email », « valeur » : « ruth.black@example.com »}], « sexe » : « féminin », « date de naissance » : « 1951-08-23 », » adresse » : [{« utiliser » : « maison », « ligne » : [« 26 Sud RdApt 22 »], « city » : « Sapulpa », « état » : « OK », « code postal » : « 74066 », « pays » : « USA »}]}, « search » : {« en mode » : « correspond à »}}]}

* * *

    Demande : GET <fhir-server>/Patient/<patient-id>
    
    Réponse : {« resourceType » : « Patient », « id » : « <patient-id> », « identificateur » : [{« utiliser » : « normal », « type » : {« codage » : [{« système » : «http://hl7.org/fhir/v2/0203», « code » : « MR »,}], « texte » : « numéro de dossier médical »}, « valeur » : « 1234567 »}], « nom » : [{« utiliser » : « officiel », » famille » : « Adams », « attribué » : [« Michel », « X ». {]}], « sexe » : « masculin », « date de naissance » : « 1925-12-23"}

* * *

Voir [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) pour plus de détails sur ce champ défini.

## <a name="observation"></a>Observation

Voici les champs obligatoires minimales, qui sont un sous-ensemble du [profil Argonaut Vital-signes](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

1. Effet (date heure ou période)
2. Code.Coding.Code
3. ValueQuantity.Value

Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :

1. Code.Coding.Display
2. ValueQuantity.Unit

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<id> patient
2. _sort =-date
3. catégorie (nous demande « catégorie = vitale signes ») pour récupérer la liste des signes vital.

Reportez-vous à cet exemple de l’appel :

* * *

    Demande : Obtenir <fhir-server>/Observation ? patient = <patient-id>&category = vitale signes
    
    Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 20, « entry » : [{« ressource » : {« resourceType » : « Observation », « id » : « <resource-id> », « catégorie » : [{« codage » : [{« système » : «http://hl7.org/fhir/observation-category», « code » : » vital-signes «}]}], « code » : {« codage » : [{« système » : «http://loinc.org», « code » : « 4 8867 », « affichage » : « heart_rate »}]}, « effectiveDateTime » : » 2009-04-08T00:00:00-06:00 », « valueQuantity » : {« valeur » : 72,0, « unité » : » {temps} / min », « système » : «http://unitsofmeasure.org»,}}},.
        .
        .
      ] }

* * *

Voir [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) pour plus de détails sur ce champ défini.

## <a name="condition"></a>Condition

Voici les champs obligatoires minimales, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

1. Code.Coding[0]. Affichage

Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :

1. AssertedDate
2. Niveau de gravité

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<id> patient
2. _count =\<results> max

Consultez l’exemple de cet appel suivant :

* * *

    Demande : Obtenir <fhir-server>/Condition ? patient = <patient-id>&_count = 10
    
    Response Group : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 2, « entry » : [{« ressource » : {« resourceType » : « Condition », « id » : « <resource-id> », « code » : {« codage » : [{« système » : «http://snomed.info/sct», « code » : « 185903001 », » afficher » : « Immunisation contre de besoins »,}]}, « severity » : {« codage » : [{« système » : «http://snomed.info/sct», « code » : « 24484000 », « afficher » : « Grave »}]}, « assertedDate » : « 2018-04-04 »}},.
        .
        .
      ] }

* * *
Voir [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) pour plus de détails sur ce champ défini.

## <a name="encounter"></a>Rencontrez

Les champs suivants sont minimales requises, qui sont un sous-ensemble des champs [profil US principaux rencontrer](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) « doit avoir »).

1. État
2. Type [0]. Codage [0]. Affichage

En outre, les champs suivants à partir du profil de nous rencontrer principaux » doivent prendre en charge » champs :

1. Period.Start
2. Emplacement [0]. Location.Display

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<id> patient
2. _sort:DESC =\<champ ex. date>
3. _count =\<results> max

L’objectif est de pouvoir récupérer l’emplacement connu dernier du patient. Chaque fait référence à une ressource d’emplacement. La référence comprennent également champ d’affichage de l’emplacement.

Voir [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) pour plus de détails sur ce champ défini.

## <a name="allergyintolerance"></a>AllergyIntolerance

Voici les champs obligatoires minimales, qui sont un sous-ensemble du profil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

1. Code.Text
2. Code.Coding[0]. Affichage
3. ClinicalStatus/VerificationStatus (lu les deux)

Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire le champ suivant :

1. AssertedDate
2. Note.Text
3. Réaction
    1. Substance (un seul élément de codage)
    2. Manifestation (un seul élément de codage)

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. Patient = \<id> patient

Consultez l’exemple de l’appel suivant : 

* * *

    Demande : Obtenir <fhir-server>/AllergyIntolerance ? patient = <patient-id>
    
    Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « AllergyIntolerance », « id » : « <resource-id> », « clinicalStatus » : « actif », « ve rificationStatus » : « confirmée », « code » : {« codage » : [{« système » : «http://rxnav.nlm.nih.gov/REST/Ndfrt», « code » : « N0000175503 », « afficher » : « sulfonamide ANTIBACTÉRIEN »,}], « texte » : ant sulfonamide » ibacterial »}, « assertedDate » : « 2018-01-01T00:00:00-07:00 », « réaction » : [{« manifestation » : [{« codage » : [{« système » : «http://snomed.info/sct», « code » :  « 271807003 », « afficher » : « éruption apparence »,}], « texte » : « éruption apparence »}],}]}}]}

* * *

Voir [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) pour plus de détails sur ce champ défini.

## <a name="medication-request"></a>Demande de médication

Voici les champs obligatoires minimales, qui sont un sous-ensemble du [profil US principaux médication demande](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

1. Medication.Display (si référence)
2. Medication.Text (si CodableConcept)
3. AuthoredOn
4. Requester.Agent.Display

Outre les champs Core américain, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :

1. DosageInstruction [.]. Texte
2. Texte

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<id> patient
2. _count =\<results> max

Voir [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) pour plus de détails sur ce champ défini.

## <a name="coverage"></a>Couverture

Voici les champs obligatoires minimales, non couverts par les profils Argonaut soit nous principaux :

1. Regroupement, au moins un élément avec
    1. Groupe IPMPAffichage
    2. PlanDisplay
2. Période
3. SubscriberId

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. Patient = \<id> patient

Voir [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) pour plus de détails sur ce champ défini.
