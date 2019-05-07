---
title: " Application des patients et DMP interface d’intégration DSTU2"
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
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643093"
---
# <a name="dstu2-interface-specification"></a>Spécification d’interface DSTU2

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Configuration ou la reconfiguration d’un serveur FHIR pour fonctionner avec l’application Microsoft équipes Patients, vous devez comprendre les données de l’application doit accéder. Le serveur FHIR doit prendre en charge les demandes POST à l’aide de groupes pour les ressources suivantes :

- [Patient](#patient)
- [Observation](#observation)
- [Condition](#condition)
- [Rencontrez](#encounter)
- [INTOLÉRANCE allergies](#allergyintolerance)
- [Couverture](#coverage)
- [Ordre de médication](#medication-order)
- [Emplacement](#location)

> [!NOTE]
> La ressource Patient est la ressource obligatoire uniquement (sans laquelle l’application chargera pas du tout. Toutefois, il est recommandé que le partenaire de mettre en œuvre la prise en charge de toutes les ressources mentionnées ci-dessus par les spécifications indiquées ci-dessous pour la meilleure expérience utilisateur final avec l’application de Patients équipes Microsoft.

Requêtes à partir de l’application Microsoft équipes Patients pour plusieurs ressources publier un lot (BATCH) des demandes à l’URL du serveur FHIR. Le serveur traite chaque demande et renvoie un ensemble de ressources correspondant à chaque demande. Pour plus d’informations et des exemples, voir [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).

Toutes les ressources FHIR suivantes doivent être accessibles par référence de ressource direct.

## <a name="conformance-minimum-required-field-set"></a>La valeur de champ obligatoire minimale de mise en conformité

 Le serveur FHIR doit implémenter la déclaration de conformité pour avoir un résumé concrètes de ses fonctionnalités. Nous pensons que les paramètres d’un serveur de FHIR DSTU2 ci-dessous :

1. REST
   1. Mode
   2. Interaction
   3. Ressource : Type
   4. Sécurité : [Extension pour les URI OAuth](http://hl7.org/fhir/extension-oauth-uris.html)
2. FhirVersion (notre code requiert cette option pour comprendre de quelle version nous devons de tableau croisé dynamique pour qu’il prend en charge plusieurs versions).

Voir [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) pour plus de détails sur ce champ défini.

## <a name="patient"></a>Patient

Voici les champs obligatoires minimales, qui sont un sous-ensemble des champs [profil patient Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

1. Name.Family
2. Name.Given
3. Sexe
4. Date de naissance
5. NRM (identificateur)

Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients lit également les champs suivants :

1. Name.Use
2. Name.Prefix
3. CareProvider (ce guide de référence sur la ressource Patient doit inclure les champs d’affichage dans l’exemple suivant.)

* * *

    Demande : GET <fhir-server>/Patient/<patient-id>
    
    Réponse : {« resourceType » : « Patient », « id » : « <patient-id>, ».
      .
      .
      « name » : [{« utiliser » : « officiel », « préfixe » : [« Mr »], « famille » : [« Chau »], « attribué » : [« Hugh »]}], « identificateur » : [{« utiliser » : « officiel », « type » : {« codage » : [{« système » : «http://hl7.org/fhir/v2/0203», « code » : « MR »}]}, « valeur » : « 1234567 »}], « sexe » : « masculin », « date de naissance » : « 1957-06-05 «, « careProvider » : [{« affichage » : « Jane Doe »}],}

* * *

Une recherche de ressource utilise la méthode POST /Patient/_search et les paramètres suivants :

1. ID
2. famille : contient = (recherche tous les patients dont le nom de famille contient la valeur).
3. donnée =\<substring>
4. nom =\<substring>
5. date de naissance =(exact match)
6. \_Count (nombre maximal de résultats qui doit être retourné) <br> La réponse doit contenir le nombre total d’enregistrements renvoyés à la suite de la recherche, et \_count utilisera le PatientsApp pour limiter le nombre d’enregistrements renvoyés.
7. identificateur =\<mrn>

L’objectif doit être en mesure de recherche et filtrage d’un patient par les éléments suivants :

- ID : Il s’agit de l’ID de ressource a toutes les ressources de FHIR.
- NRM : Il s’agit de l’identificateur pour le patient personnel savez réel. Nous savons que ce NRM est basé sur le type d’identificateur à l’intérieur de la ressource de l’identificateur dans FHIR
- Nom
- Date de naissance

Voir l’exemple suivant de cet appel.

* * *

    Requête : Corps de la demande POST <fhir-server>/Patient/_search : donnée = hugh&family = chau
    
    Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id>, ».
      .
      .
      « entry » : [{« ressource » : {« resourceType » : « Patient », « id » : « <patient-id> », « nom » : [{« texte » : « Hugh Chau », « famille » : [« Chau »], « attribué » : [« Hugh »]}], « sexe » : « masculin », « date de naissance » : « 1957-06-05 »}, « search » : {« mode » : « correspond à »}}]}

* * *

Voir [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) pour plus de détails sur ce champ défini.

## <a name="observation"></a>Observation

Voici les champs obligatoires minimales, qui sont un sous-ensemble du profil Argonaut signes essentielles :

 1. Effet (date heure ou période)
 2. Code.Coding.Code
 3. ValueQuantity.Value

Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients lit également les champs suivants :

 1. Code.Coding.Display
 2. ValueQuantity.Unit

Si vous utilisez des observations composant, la même logique s’applique pour observation de chaque composant.

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<id patient\>
2. tri : desc =\<champ ex. date\>

L’objectif doit être en mesure de récupérer les signes vital le plus récent pour un patient, [VitalSigns.DSTU.saz] (observation ?).

* * *

    Demande : Obtenir <fhir-server>/Observation ? patient = <patient-id>&_sort:desc = date&category = vitale signes
    
    Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 20, « entry » : [{« ressource » : {« resourceType » : « Observation », « id » : « <resource-id> », « catégorie » : {« codage » : [{code » : « vitale signes »}],}, « code » : { » codage » : [{« système » : «http://loinc.org», « code » : « 39156-5 », « affichage » : « IMC »}],}, « effectiveDateTime » : « 2009-12-01 », « valueQuantity » : {« valeur » : 34.4, « unité » : « kg/m2 », « système » : «http://unitsofmeasure.org», « code » : « kg/m2 »}},},.
        .
        .
      ] }

* * *

Voir [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) pour plus de détails sur ce champ défini.

## <a name="condition"></a>Condition

Voici les champs obligatoires minimales, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code.Coding[0]. Affichage

Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :

1. Date d’enregistrement
2. Niveau de gravité

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<id> patient
2. _count =\<results> max

Consultez l’exemple de cet appel suivant :

* * *

    Demande : Obtenir <fhir-server>/Condition ? patient = <patient-id>&_count = 10
    
    Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « Condition », « id » : « <resource-id> », « code » : {« codage » : [{               « système » : «http://snomed.info/sct», « code » : « 386033004 », « afficher » : « NEUROPATHIE (nerf) »}]}, « dateRecorded » : « 2018-09-17 », « severity » : {« codage » : [{ » le système cadratin » : «http://snomed.info/sct», « code » : « 24484000 », « afficher » : « Grave »}]}},}]}

* * *

Voir [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) pour plus de détails sur ce champ défini.

## <a name="encounter"></a>Rencontrez

Voici les champs obligatoires minimales, qui sont un sous-ensemble des champs « doit avoir » profil nous rencontrer principaux :

1. État
2. Type [0]. Codage [0]. Affichage

En outre, les champs suivants à partir du profil de nous rencontrer principaux » doivent prendre en charge » de champs

1. Period.Start
2. Emplacement [0]. Location.Display

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<id> patient
2. _sort:DESC =\<champ ex. date>
3. _count =\<results> max

L’objectif est de pouvoir récupérer l’emplacement connu dernier du patient. Chaque fait référence à une ressource d’emplacement. La référence comprennent également champ d’affichage de l’emplacement. Voir l’exemple suivant de cet appel.
* * *

    Demande : Obtenir <fhir-server>/rencontre ? patient = <patient-id>&_sort:desc = date&_count = 1
    
    Réponse : {« resourceType » : « Groupement », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « Rencontrer », « id » : « <resource-id> », « identificateur » : [{« utiliser » : « officiel », « valeur » : «<id>»}], « status » : « a », « type » : [{« codage » : [{« affichage » : « Rendez-vous »}],}], « patients » : {« référence » : « Patient/<patient-id> »}, « période » : {« Démarrer » : « 17/09/2018 1:00:00 PM »}, « emplacement » : [{              « emplacement » : {« affichage » : « Cours pratique – ENT »},}]}}]}

* * *

Voir [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) pour plus de détails sur ce champ défini.

## <a name="allergyintolerance"></a>AllergyIntolerance

Voici les champs obligatoires minimales, qui sont un sous-ensemble du profil Argonaut AllergyIntolerance :

1. Code.Text
2. Code.Coding[0]. Affichage
3. État

Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients lit également les champs suivants :

1. RecordedDate
2. Note.Text
3. Réaction [.]. Substance.Text
4. Réaction [.]. Manifestation [.]. Texte
5. Text.Div

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. Patient = \<id> patient

Consultez l’exemple de cet appel suivant :

* * *

    Demande : Obtenir <fhir-server>/AllergyIntolerance ? patient = <patient-id>
    
    Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « AllergyIntolerance », « id » : « <resource-id> », « recordedDate » : « 2018-09-17T07:00:00.00 0Z », « substance » : {« texte » : « Cajou »}, « status » : « confirmée », « réaction » : [{« substance » : {« texte » : « écrou cajou allergisants extraire produit Injectable »}, manifestati » sur » : [{« texte » : « Réaction Anaphylactic »}]}]}}]}

* * *

Voir [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) pour plus de détails sur ce champ défini.

## <a name="medication-order"></a>Ordre de médication

Voici les champs obligatoires minimales, qui sont un sous-ensemble du profil Argonaut MedicationOrder :

1. DateWritten
2. Prescriber.Display
3. Medication.Display (si référence)
4. Medication.Text (si concept)

Outre les champs Argonaut, pour une expérience utilisateur satisfaisante l’application de Patients permettre également lire les champs suivants :

1. DateEnded
2. DosageInstruction.Text
3. Text.Div

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<id> patient
2. _count =\<results> max

Consultez l’exemple de cet appel suivant :

* * *

    Demande : Obtenir <fhir-server>/MedicationOrder ? patient = <patient-id>&_count = 10
    
    Réponse : {« resourceType » : « Regroupent », « id » : « <bundle-id> », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « MedicationOrder », « id » : « <resource-id> », « dateWritten » : « 2018-09-17 », « medi cationCodeableConcept » : {« texte » : « Lisinopril 20 MG orale Tablet »}, « prescriber » : {« affichage » : « Jane Doe »}, « dosageInstruction » : [{« texte » : « 1 jour »}]}}]}

* * *  

Voir [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) pour plus de détails sur ce champ défini.

## <a name="coverage"></a>Couverture

Voici les champs obligatoires minimales, non couverts par les profils Argonaut soit nous principaux :

1. Organismes payeurs

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

1. patient =\<id> patient

Consultez l’exemple de cet appel suivant :

* * *

    Demande : Obtenir une <fhir-server>/couverture ? patient = <patient-id>
    
    Réponse : {« resourceType » : « Groupement », « type » : « searchset », « total » : 1, « entry » : [{« ressource » : {« resourceType » : « Couverture », « id » : « <resource-id> », « plan » : « No principal d’assurance », « abonné » : {« référence » : « Patient / <patient-id> »}}}]}

* * *

Voir [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) pour plus de détails sur ce champ défini.

## <a name="location"></a>Lieu

Cette ressource est uniquement utilisée comme une référence à la ressource de [rencontrer](#encounter) .

Voir [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) pour plus de détails sur ce champ défini.
