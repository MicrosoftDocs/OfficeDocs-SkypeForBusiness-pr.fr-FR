---
title: Interface De l’application Patients et de l’intégration EHR
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
description: Découvrez comment intégrer des enregistrements d’état d’santé électroniques à l Microsoft Teams patient et à la spécification de l’interface SPECIFICATION3.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803492"
---
# <a name="stu3-interface-specification"></a>Spécification de l’interface STU3

> [!NOTE]
> À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui soutien l’équipe. Toutes les données associées à l’application Patients sont conservées dans ce groupe mais ne sont plus accessibles via l’interface utilisateur. Les utilisateurs peuvent re-créer leurs listes à l’aide de l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Les listes permet aux équipes de soins de votre organisation de santé de créer des listes de patients pour différents scénarios (arrondis, réunions d’équipe de formation, surveillance générale des patients, etc.). Pour commencer, consultez le modèle Patients dans listes. Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, consultez [Gérer l’application Listes](../../manage-lists-app.md).

La configuration ou la reconfiguration d’un serveur FEMBA pour l’Microsoft Teams Patients nécessite de comprendre les données dont l’application a besoin pour accéder. Le serveur F POSTER doit prendre en charge les demandes POST qui utilisent des offres groupées pour les ressources suivantes :

- [Patient](#patient)
- [Observation](#observation)
- [Condition](#condition)
- [Rencontrer](#encounter)
- [Erdesses](#allergyintolerance)
- [Couverture](#coverage)
- [Relevé de médication](#medication-request) (remplace l’ordre Médication dans la version DSTU2 de l’app Patients)
- Emplacement (les informations requises pour cette ressource peuvent être incluses dans La Rencontre)

> [!NOTE]
> La ressource patient est la seule ressource obligatoire (sans laquelle l’application ne se charge pas du tout) ; Toutefois, il est recommandé au partenaire d’implémenter la prise en charge de toutes les ressources ci-dessus mentionnées par spécifications fournies ci-dessous pour une expérience utilisateur la plus agréable avec l’application Microsoft Teams Patients.

Les requêtes de l’Microsoft Teams Patients pour plusieurs ressources publient une offre groupée (BATCH) de demandes sur l’URL du serveur F URL. Le serveur doit traiter chaque demande et renvoyer une offre groupée de ressources correspondent à chaque demande. Pour plus d’informations et d’exemples, [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) voir .

## <a name="capability-statement"></a>Instruction de fonctionnalité

Voici les champs minimum requis :

 - REST

    - Mode
    - Interaction
    - Ressource : Type
    - Sécurité : [Extension pour les UR OAuth](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FembaVersion (notre code nécessite que l’on comprenne la version vers laquelle nous devons pivoter).

Consultez [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) d’autres informations sur ce jeu de champs.

## <a name="patient"></a>Patient

Voici les champs minimum requis, qui sont un sous-ensemble des champs de profil du patient Argot :

 - Name.Given
 - Name.Family
 - Sexe
 - Date BirthDate
 - MRN (identificateur)

Outre les champs [Argot,](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)pour une grande expérience utilisateur, l’application Patients peut également lire les champs suivants :

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner] - La référence du generalPractitioner doit être incluse dans la ressource patient (champ d’affichage uniquement)

Une recherche de ressources utilise la méthode POST à /Patient/_search et les paramètres suivants :

 - id
 - family=(recherche tous les patients dont le nom de famille contient la valeur)
 - given=\<substring>
 - birthdate=(correspondance exacte)
 - gender=(valeurs l’une des administratives-sexe)
 - \_nombre (nombre maximal de résultats à retourner) <br> La réponse doit contenir le nombre total d’enregistrements renvoyés suite à la recherche et le nombre sera utilisé par l’App Patients pour limiter le nombre d’enregistrements \_ renvoyés.
 - identifier=\<mrn>

L’objectif est de pouvoir rechercher et filtrer un patient comme suit :

- N° : il s’agit de l’ID de ressource dont dispose chaque ressource de l’affectation FEMBA.
- MRN : il s’agit de l’identificateur réel du patient que le personnel clinique connaît. Nous comprenons que cette fonction MRN est basée sur le type d’identificateur à l’intérieur de la ressource d’identificateur dans FEMBA.
- Nom
- Date de naissance

Consultez l’exemple suivant de l’appel :

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

Consultez [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) d’autres informations sur ce jeu de champs.

## <a name="observation"></a>Observation

Il s’agit des champs requis au minimum, qui sont un sous-ensemble du profil [Vital-Signs argotaïques.](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)

 - Effectif (date ou période)
 - Code.Coding.Code
 - ValueQuantity.Value

Outre les champs Argot, pour une grande expérience utilisateur, l’application Patients peut également lire les champs suivants :

 - Code.Coding.Display
 - ValueQuantity.Unit

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - patient=\<patient id>
 - _sort=date
 - catégorie (nous interrogerons « category=signes vital ») pour récupérer la liste des signes vital.

Reportez-vous à cet exemple d’appel :

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

Consultez [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) d’autres informations sur ce jeu de champs.

## <a name="condition"></a>Condition

Voici les champs minimaux requis, qui sont un sous-ensemble du profil [de condition argotaïques.](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)

 - Code.Coding[0]. Affichage

Outre les champs Argot, pour une grande expérience utilisateur, l’application Patients peut également lire les champs suivants :

 - AréoedDate
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

Consultez [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) d’autres informations sur ce jeu de champs.

## <a name="encounter"></a>Rencontrer

Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs « must have » du profil [US Core Encounter).](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)

 - État
 - Tapez[0]. Codage[0]. Affichage

De plus, les champs suivants des champs « doivent prendre en charge » du profil US Core Encounter :

 - Point.Début
 - Emplacement[0]. Location.Display

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - patient=\<patient id>
 - _sort:desc=\<field ex. date>
 - _count=\<max results>

L’objectif est de pouvoir récupérer le dernier emplacement connu du patient. Chaque rencontre fait référence à une ressource d’emplacement. La référence doit également inclure le champ d’affichage de l’emplacement.

Consultez [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) d’autres informations sur ce jeu de champs.

## <a name="allergyintolerance"></a>MondeYIntolerance

Il s’agit des champs requis au minimum, qui sont un sous-ensemble du profil [d’argotaïeIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) :

 - Code.Text
 - Code.Coding[0]. Affichage
 - État clinique/État De vérification (nous lisons les deux)

Outre les champs Argot, pour une grande expérience utilisateur, l’application Patients peut également lire le champ suivant :

 - AréoedDate
 - Note.Text
 - Réaction
    - Substance (un élément de codage)
    - Environ (un élément de codage)

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - Patient =  \<patient id>

Consultez l’exemple suivant de l’appel : 

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

Consultez [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) d’autres informations sur ce jeu de champs.

## <a name="medication-request"></a>Demande de médication

Voici les champs minimum requis, qui sont un sous-ensemble du profil de demande de médication de base [pour les États-Unis](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):

 - Medication.Display (si référence)
 - Medication.Text (siConceptable)
 - AuthoredOn
 - Requester.Agent.Display

Outre les champs cœur des États-Unis, pour une expérience utilisateur excellente, l’application Patients peut également lire les champs suivants :

 - [.]. Texte
 - Texte

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - patient=\<patient id>
 - _count=\<max results>

Consultez [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) d’autres informations sur ce jeu de champs.

## <a name="coverage"></a>Couverture

Il s’agit des champs requis au minimum, et non couverts par les profils Us Core ou Argot :

 - Regroupement, au moins un élément avec
    - GroupDisplay
    - PlanDisplay
 - Point
 - SubscriberId

Une recherche de ressources utilise la méthode GET et les paramètres suivants :

 - Patient = \<patient id>

Consultez [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) d’autres informations sur ce jeu de champs.
