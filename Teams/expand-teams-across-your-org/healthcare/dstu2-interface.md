---
title: Interface DSTU2 de l’application Patients et de l’intégration EHR
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Découvrez la spécification de l’interface DSTU2 dans Teams, y compris la configuration ou la reconfiguration d’un serveur FEMBA pour l’utiliser avec l’application Microsoft Teams Patients.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3d4b8e1d965cd3b0704885d6f86e376cfc3c9316
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589728"
---
# <a name="dstu2-interface-specification"></a>Spécification de l’interface DSTU2

> [!NOTE]
> À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui soutien l’équipe. Toutes les données associées à l’application Patients sont conservées dans ce groupe mais ne sont plus accessibles via l’interface utilisateur. Les utilisateurs peuvent re-créer leurs listes à l’aide de l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Les listes permet aux équipes de soins de votre organisation de santé de créer des listes de patients pour différents scénarios (arrondis, réunions d’équipe de formation, surveillance générale des patients, etc.). Pour commencer, consultez le modèle Patients dans listes. Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, consultez [Gérer l’application Listes](../../manage-lists-app.md).

La configuration ou la reconfiguration d’un serveur FEMBA pour l’Microsoft Teams Patients nécessite de comprendre les données dont l’application a besoin pour accéder. Le serveur F POSTER doit prendre en charge les demandes POST qui utilisent des offres groupées pour les ressources suivantes :

- [Patient](#patient)
- [Observation](#observation)
- [Condition](#condition)
- [Rencontrer](#encounter)
- [10000000](#allergyintolerance)
- [Couverture](#coverage)
- [Ordre des médications](#medication-order)
- [Emplacement](#location)

> [!NOTE]
> La ressource patient est la seule ressource obligatoire (sans laquelle l’application ne se charge pas du tout. Toutefois, il est recommandé au partenaire d’implémenter la prise en charge de toutes les ressources ci-dessus mentionnées par spécifications fournies ci-dessous pour une expérience utilisateur la plus agréable avec l’application Microsoft Teams Patients.

Requêtes de l’Microsoft Teams Patients de plusieurs ressources publient une offre groupée (BATCH) de demandes vers l’URL du serveur FEMBA. Le serveur traite chaque demande et renvoie une offre groupée de ressources correspondent à chaque demande. Pour plus d’informations et d’exemples, [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) voir .

Toutes les ressources D FEMBA suivantes doivent être accessibles à l’aide d’une référence de ressource directe.

## <a name="conformance-minimum-required-field-set"></a>Ensemble de champs requis au minimum pour la conformité

 Pour pouvoir obtenir un résumé factuel de ses fonctionnalités, le serveur FEMBA doit implémenter la déclaration de conformité. Nous attendons les paramètres suivants dans un serveur DSTU2 FEMBA :

 - REST

    - Mode
    - Interaction
    - Ressource : Type
    - Sécurité : [Extension pour les UR OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FembaVersion (notre code exige que l’on comprenne la version vers laquelle nous devons pivoter, car nous prise en charge les versions multiples).

Consultez [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) d’autres informations sur ce jeu de champs.

## <a name="patient"></a>Patient

Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs de profil [du patient Argot](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

 - Name.Family
 - Name.Given
 - Sexe
 - Date BirthDate
 - MRN (identificateur)

Outre les champs Argot, pour une expérience utilisateur excellente, l’application Patients lit également les champs suivants :

 - Name.Use
 - Name.Prefix
 - CareProvider (cette référence sur la ressource du patient doit inclure les champs d’affichage illustrés dans l’exemple suivant.)

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

Une recherche de ressources utilise la méthode POST à /Patient/_search et les paramètres suivants :

 - id
 - family:contains=(recherche tous les patients dont le nom de famille contient la valeur.)
 - given=\<substring>
 - name=\<substring>
 - birthdate=(correspondance exacte)
 - \_nombre (nombre maximal de résultats à retourner) <br> La réponse doit contenir le nombre total d’enregistrements renvoyés suite à la recherche, et le nombre sera utilisé par l’App Patients pour limiter le nombre d’enregistrements \_ renvoyés.
 - identifier=\<mrn>

L’objectif est de pouvoir rechercher et filtrer un patient comme suit :

- N° : il s’agit de l’ID de ressource dont dispose chaque ressource de l’affectation FEMBA.
- MRN : il s’agit de l’identificateur réel du patient que le personnel clinique connaît. Nous comprenons que cette fonction MRN est basée sur le type d’identificateur à l’intérieur de la ressource d’identificateur dans FEMBA
- Nom
- Date de naissance

Consultez l’exemple suivant de cet appel.

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

Consultez [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) d’autres informations sur ce jeu de champs.

## <a name="observation"></a>Observation

Il s’agit des champs requis au minimum, qui sont un sous-ensemble du profil des signes vital d’Argot :

 - Effectif (date ou période)
 - Code.Coding.Code
 - ValueQuantity.Value

Outre les champs Argot, pour une expérience utilisateur excellente, l’application Patients lit également les champs suivants :

 - Code.Coding.Display
 - ValueQuantity.Unit

Si vous utilisez des observations de composant, la même logique s’applique à chaque observation de composant.

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - patient=\<patient id\>
 - sort:desc=\<field ex. date\>

L’objectif est de pouvoir récupérer les derniers signes essentiels d’un patient, [VitalSigns.DSTU.saz] (observation ?).

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

Consultez [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) d’autres informations sur ce jeu de champs.

## <a name="condition"></a>Condition

Voici les champs requis au minimum, qui sont un sous-ensemble du profil [de condition Argot :](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

1. Code.Coding[0]. Affichage

Outre les champs Argot, pour une grande expérience utilisateur, l’application Patients peut également lire les champs suivants :

 - Date enregistrée
 - Gravité

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - patient=\<patient id>
 - _count=\<max results>

Consultez l’exemple suivant de cet appel :

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

Consultez [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) d’autres informations sur ce jeu de champs.

## <a name="encounter"></a>Rencontrer

Voici les champs minimum requis, qui sont un sous-ensemble des champs « must have » du profil US Core Encounter :

 - Statut
 - Tapez[0]. Codage[0]. Affichage

En outre, les champs suivants des champs « doivent prendre en charge » du profil US Core Encounter

 - Point.Début
 - Emplacement[0]. Location.Display

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

L’objectif est de pouvoir récupérer le dernier emplacement connu du patient. Chaque rencontre fait référence à une ressource d’emplacement. La référence doit également inclure le champ d’affichage de l’emplacement. Consultez l’exemple suivant de cet appel.

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

Consultez [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) d’autres informations sur ce jeu de champs.

## <a name="allergyintolerance"></a>MondeYIntolerance

Il s’agit des champs requis au minimum, qui sont un sous-ensemble du profil ArgotaïquesIntolerance :

 - Code.Text
 - Code.Coding[0]. Affichage
 - Statut

Outre les champs Argot, pour une expérience utilisateur excellente, l’application Patients lit également les champs suivants :

 - RecordedDate
 - Note.Text
 - Réaction[..]. Substance.Text
 - Réaction[..]. [.]. Texte
 - Text.Div

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - Patient =  \<patient id>

Consultez l’exemple suivant de cet appel :

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

Consultez [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) d’autres informations sur ce jeu de champs.

## <a name="medication-order"></a>Ordre des médications

Voici les champs minimaux requis, qui sont un sous-ensemble du profil Médicaux d’Argot :

 - DateWritten
 - Enr.Affichage
 - Medication.Display (référence de cas)
 - Médication.texte (concept de cas)

Outre les champs Argot, pour une grande expérience utilisateur, l’application Patients peut également lire les champs suivants :

 - DateEnded
 - Onstruction.Text
 - Text.Div

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - patient=\<patient id>
 - _count=\<max results>

Consultez l’exemple suivant de cet appel :

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

Consultez [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) d’autres informations sur ce jeu de champs.

## <a name="coverage"></a>Couverture

Voici les champs requis au minimum, et non couverts par les profils Us Core ou Argot :

 - Payeur

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - patient=\<patient id>

Consultez l’exemple suivant de cet appel :

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
Consultez [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) d’autres informations sur ce jeu de champs.

## <a name="location"></a>Lieu

Cette ressource n’est utilisée qu’en tant que référence sur la [ressource Rencontrer.](#encounter)

Consultez [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) d’autres informations sur ce jeu de champs.
