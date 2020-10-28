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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a36c6176b4873dd41d654493bd36e9a3dbbfd49a
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772265"
---
# <a name="stu3-interface-specification"></a>Spécification de l’interface STU3

> [!NOTE]
> À compter du 30 octobre 2020, l’application patients a été supprimée et remplacée par l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Dans le cas des listes, les équipes de soins de votre organisation peuvent créer des listes de patients dans le cas de signes et de réunions d’équipe de manière générale. Consultez le modèle patients dans les listes pour commencer. Pour en savoir plus sur la gestion de l’application listes au sein de votre organisation, voir [gérer l’application listes](../../manage-lists-app.md).

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

Les requêtes à partir de l’application patients de Microsoft teams pour plusieurs ressources publient une offre (BATCH) de requêtes dans l’URL du serveur FHIR. Le serveur traitera chaque demande et renverra une offre de ressources correspondant à chaque demande. Pour plus d’informations et d’exemples, voir [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) .

## <a name="capability-statement"></a>Instruction Capability

Voici les champs obligatoires obligatoires :

 - LAISSER

    - Veille
    - Interaction
    - Ressource : type
    - Sécurité : [extension pour les URI OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (notre code nécessite cela pour comprendre la version à laquelle nous devons faire pivoter.)

[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="patient"></a>Patient

Voici les champs requis au minimum, qui sont un sous-ensemble des champs du profil du patient Argonaut :

 - Nom. fourni
 - Name. Family
 - Public
 - Anniversaire
 - NRM (identificateur)

Outre les [champs Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

 - Name. use
 - Nom. préfixe
 - [GeneralPractitioner] : la référence GeneralPractitioner doit être incluse dans la ressource patient (champ d’affichage uniquement)

Une recherche de ressource utilise la méthode POST à/patient/_search et les paramètres suivants :

 - ID
 - famille = (recherche tous les patients dont le nom de famille contient la valeur)
 - accordé =\<substring>
 - DateNaissance = (correspondance exacte)
 - sexe = (valeurs faisant partie d’un compte d’administrateur-sexe)
 - \_nombre (nombre maximal de résultats à renvoyer) <br> La réponse doit contenir le nombre total d’enregistrements renvoyés comme résultat de la recherche et du \_ comptage qui seront utilisés par le PatientsApp pour limiter le nombre d’enregistrements renvoyés.
 - identificateur =\<mrn>

L’objectif est de pouvoir Rechercher et filtrer un patient en procédant comme suit :

- ID : il s’agit de l’ID de ressource dont se trouve chaque ressource dans FHIR.
- NRM : il s’agit de l’identificateur réel du patient que le personnel expérimenté connaîtait. Nous comprenons que ce NRM est basé sur le type d’identificateur figurant à l’intérieur de la ressource d’identificateur dans FHIR.
- Nom
- Anniversaire

Pour plus d’informations, reportez-vous à l’exemple suivant :

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="observation"></a>Déterminée

Il s’agit des champs requis au minimum, qui sont un sous-ensemble de [Argonaut Vital-Signs profil](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).

 - Effective (heure de date ou période)
 - Code. Coding. code
 - ValueQuantity. Value

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

 - Code. Coding. Display
 - ValueQuantity. Unit

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - patient =\<patient id>
 - _sort = date
 - Category (nous interrogerons « Category = vitaux-Sign-signes ») pour récupérer la liste des signes vitaux.

Reportez-vous à cet exemple de l’appel :

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="condition"></a>Condition

Voici les champs requis au minimum, qui sont un sous-ensemble du [profil de condition Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).

 - Code. Coding [0]. 3D

Outre les champs Argonaut, pour une bonne utilisation de l’utilisateur, l’application patients peut également lire les champs suivants :

 - AssertedDate
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
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="encounter"></a>Connaître

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble des champs du profil de type [rencontrent des États-Unis](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) .

 - État
 - Tapez [0]. Code [0]. 3D

De plus, les champs suivants provenant du cœur Microsoft pour les États-Unis du profil « doivent prendre en charge » :

 - Période. début
 - Emplacement [0]. Emplacement. Display

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - patient =\<patient id>
 - _sort : DESC =\<field ex. date>
 - _count =\<max results>

L’objectif est de pouvoir récupérer le dernier emplacement connu du patient. Chaque rencontre fait référence à une ressource d’emplacement. La référence inclut également le champ d’affichage de l’emplacement.

[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="allergyintolerance"></a>AllergyIntolerance

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du profil [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

 - Code. Text
 - Code. Coding [0]. 3D
 - ClinicalStatus/VerificationStatus (nous avons lu les deux)

Outre les champs Argonaut, pour optimiser l’utilisation de l’application patients, l’application patients peut également lire le champ suivant :

 - AssertedDate
 - Remarque. Text
 - Réaction
    - Substance (un élément de codage)
    - Manifeste (un élément de codage)

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="medication-request"></a>Demande de médication

Il s’agit des champs obligatoires minimum, qui sont un sous-ensemble du [profil de demande de médicament principal pour les États-Unis](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

 - Médication. Display (Si référence)
 - Médication. Text (si CodableConcept)
 - AuthoredOn
 - Demandeur. agent. Display

Outre les champs de base américaine, l’application patients peut également lire les champs suivants pour une utilisation optimale :

 - DosageInstruction[..]. Synthèse
 - Synthèse

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - patient =\<patient id>
 - _count =\<max results>

[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)Pour plus d’informations sur ce jeu de champs, voir.

## <a name="coverage"></a>Articles

Il s’agit des champs requis au minimum, qui ne sont pas couverts par les profils Argonaut ou les profils américains suivants :

 - Regroupement d’au moins un élément avec
    - GroupDisplay
    - PlanDisplay
 - Donnée
 - SubscriberId

Une recherche de ressource utilise la méthode GET et les paramètres suivants :

 - Patient = \<patient id>

[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)Pour plus d’informations sur ce jeu de champs, voir.
