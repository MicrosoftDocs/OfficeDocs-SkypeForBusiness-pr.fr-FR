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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 15bcc5fcaff50d6d41c45ef2d38e34719ebca999
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772205"
---
# <a name="dstu2-interface-specification"></a>Spécification de l’interface DSTU2

> [!NOTE]
> À compter du 30 octobre 2020, l’application patients a été supprimée et remplacée par l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Dans le cas des listes, les équipes de soins de votre organisation peuvent créer des listes de patients dans le cas de signes et de réunions d’équipe de manière générale. Consultez le modèle patients dans les listes pour commencer. Pour en savoir plus sur la gestion de l’application listes dans votre organisation, voir [gérer l’application listes](../../manage-lists-app.md) .

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

 - LAISSER

    - Veille
    - Interaction
    - Ressource : type
    - Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (notre code nécessite une telle mesure pour savoir quelle version nous devons faire pivoter à mesure que nous prenons en charge plusieurs versions.)

[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="patient"></a>Patient

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du [Profil du patient Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :

 - Name. Family
 - Nom. fourni
 - Public
 - Anniversaire
 - NRM (identificateur)

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :

 - Name. use
 - Nom. préfixe
 - CareProvider (cette référence sur la ressource patient doit inclure les champs d’affichage illustrés dans l’exemple suivant.)

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

Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :

 - ID
 - famille : contient = (recherche les patients dont le nom de famille contient la valeur.)
 - accordé =\<substring>
 - Name =\<substring>
 - DateNaissance = (correspondance exacte)
 - \_nombre (nombre maximal de résultats à renvoyer) <br> La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche, et \_ le nombre sera utilisé par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.
 - identificateur =\<mrn>

L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :

- ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.
- NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait. Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR
- Nom
- Anniversaire

Pour plus d’informations, reportez-vous à l’exemple suivant.

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

[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="observation"></a>Déterminée

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil de signes vitaux de Argonaut :

 - Effective (heure de date ou période)
 - Code. Coding. code
 - ValueQuantity. Value

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :

 - Code. Coding. Display
 - ValueQuantity. Unit

S’il s’agit d’une observation de composant, la même logique s’applique à chaque composant d’observation.

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - patient =\<patient id\>
 - Trier : DESC =\<field ex. date\>

L’objectif est de pouvoir récupérer les derniers signes vitaux pour un patient, [VitalSigns. DSTU. saz] (observation ?).

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

[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="condition"></a>Condition

Il s’agit des champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):

1. Code. Coding [0]. 3D

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

 - Date d’enregistrement
 - Minimal

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - patient =\<patient id>
 - _count =\<max results>

Pour plus d’informations, reportez-vous à l’exemple suivant :

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

[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="encounter"></a>Connaître

Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs du profil de rencontre du cœur américain « doivent avoir » des champs :

 - État
 - Tapez [0]. Code [0]. 3D

De plus, les champs suivants provenant des champs du profil « doit prendre en charge » sont les suivants :

 - Période. début
 - Emplacement [0]. Emplacement. Display

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - patient =\<patient id>
 - _sort : DESC =\<field ex. date>
 - _count =\<max results>

L’objectif est de pouvoir récupérer le dernier emplacement connu du patient. Chaque rencontre fait référence à une ressource d’emplacement. La référence inclut également le champ d’affichage de l’emplacement. Pour plus d’informations, reportez-vous à l’exemple suivant.

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

[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="allergyintolerance"></a>AllergyIntolerance

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut AllergyIntolerance :

 - Code. Text
 - Code. Coding [0]. 3D
 - État

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients lit également les champs suivants :

 - RecordedDate
 - Remarque. Text
 - Réaction [...]. Substance. texte
 - Réaction [...]. Manifeste [...]. Synthèse
 - Text. div

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - Patient =  \<patient id>

Pour plus d’informations, reportez-vous à l’exemple suivant :

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

[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="medication-order"></a>Ordre de médication

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil Argonaut MedicationOrder :

 - DateWritten
 - Ordonnateur. Display
 - Médication. Display (Si référence)
 - Medication. Text (si concept)

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

 - DateEnded
 - DosageInstruction. Text
 - Text. div

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - patient =\<patient id>
 - _count =\<max results>

Pour plus d’informations, reportez-vous à l’exemple suivant :

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

[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="coverage"></a>Articles

Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :

 - Payor

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - patient =\<patient id>

Pour plus d’informations, reportez-vous à l’exemple suivant :

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
    
[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="location"></a>Lieu

Cette ressource est uniquement utilisée comme référence sur la ressource de [rencontre](#encounter) .

[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)Pour plus d’informations sur ce jeu de champs, voir.
