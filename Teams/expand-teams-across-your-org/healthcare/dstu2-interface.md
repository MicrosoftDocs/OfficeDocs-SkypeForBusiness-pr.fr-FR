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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Découvrez la spécification de l’interface DSTU2 dans Teams, y compris la configuration ou la reconfiguration d’un serveur FEMBA pour l’utiliser avec l’application Patients de Microsoft Teams.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803482"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="72922-103">Spécification de l’interface DSTU2</span><span class="sxs-lookup"><span data-stu-id="72922-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="72922-104">À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’application [Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams.</span><span class="sxs-lookup"><span data-stu-id="72922-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="72922-105">Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui constitue le fond de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="72922-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="72922-106">Toutes les données associées à l’application Patients sont conservées dans ce groupe, mais ne peuvent plus être accessibles via l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="72922-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="72922-107">Les utilisateurs peuvent re-créer leurs listes à l’aide de [l’application Listes.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="72922-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="72922-108">Avec les listes, les équipes de soins de votre organisation de soins de santé peuvent créer des listes de patients pour des scénarios allant des arrondis et des réunions d’équipe de recherche à la surveillance générale des patients.</span><span class="sxs-lookup"><span data-stu-id="72922-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="72922-109">Consultez le modèle Patients dans Listes pour commencer.</span><span class="sxs-lookup"><span data-stu-id="72922-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="72922-110">Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, voir [l’application Gérer les listes.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="72922-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="72922-111">La configuration ou la reconfiguration d’un serveur FEMBA pour qu’il fonctionne avec l’application Patients de Microsoft Teams nécessite de comprendre les données dont l’application a besoin pour accéder.</span><span class="sxs-lookup"><span data-stu-id="72922-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="72922-112">Le serveur F POSTER doit prendre en charge les demandes POST qui utilisent des offres groupées pour les ressources suivantes :</span><span class="sxs-lookup"><span data-stu-id="72922-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="72922-113">Patient</span><span class="sxs-lookup"><span data-stu-id="72922-113">Patient</span></span>](#patient)
- [<span data-ttu-id="72922-114">Observation</span><span class="sxs-lookup"><span data-stu-id="72922-114">Observation</span></span>](#observation)
- [<span data-ttu-id="72922-115">Condition</span><span class="sxs-lookup"><span data-stu-id="72922-115">Condition</span></span>](#condition)
- [<span data-ttu-id="72922-116">Rencontrer</span><span class="sxs-lookup"><span data-stu-id="72922-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="72922-117">10000000</span><span class="sxs-lookup"><span data-stu-id="72922-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="72922-118">Couverture</span><span class="sxs-lookup"><span data-stu-id="72922-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="72922-119">Ordre des médications</span><span class="sxs-lookup"><span data-stu-id="72922-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="72922-120">Emplacement</span><span class="sxs-lookup"><span data-stu-id="72922-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="72922-121">La ressource patient est la seule ressource obligatoire (sans laquelle l’application ne se charge pas du tout.</span><span class="sxs-lookup"><span data-stu-id="72922-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="72922-122">Toutefois, il est recommandé au partenaire d’implémenter la prise en charge de toutes les ressources mentionnées ci-dessus par spécifications fournies ci-dessous pour une expérience utilisateur la plus agréable avec l’application Microsoft Teams Patients.</span><span class="sxs-lookup"><span data-stu-id="72922-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="72922-123">Requêtes de l’application Patients de Microsoft Teams pour plusieurs ressources publient une offre groupée (BATCH) de demandes vers l’URL du serveur FEMBA.</span><span class="sxs-lookup"><span data-stu-id="72922-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="72922-124">Le serveur traite chaque demande et renvoie une offre groupée de ressources correspondent à chaque demande.</span><span class="sxs-lookup"><span data-stu-id="72922-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="72922-125">Pour plus d’informations et d’exemples, [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) voir .</span><span class="sxs-lookup"><span data-stu-id="72922-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="72922-126">Toutes les ressources D FEMBA suivantes doivent être accessibles par référence de ressource directe.</span><span class="sxs-lookup"><span data-stu-id="72922-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="72922-127">Ensemble de champs requis au minimum pour la conformité</span><span class="sxs-lookup"><span data-stu-id="72922-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="72922-128">Pour pouvoir obtenir un résumé factuel de ses fonctionnalités, le serveur FEMBA doit implémenter la déclaration de conformité.</span><span class="sxs-lookup"><span data-stu-id="72922-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="72922-129">Nous attendons les paramètres suivants dans un serveur DSTU2 FEMBA :</span><span class="sxs-lookup"><span data-stu-id="72922-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="72922-130">REST</span><span class="sxs-lookup"><span data-stu-id="72922-130">REST</span></span>

    - <span data-ttu-id="72922-131">Mode</span><span class="sxs-lookup"><span data-stu-id="72922-131">Mode</span></span>
    - <span data-ttu-id="72922-132">Interaction</span><span class="sxs-lookup"><span data-stu-id="72922-132">Interaction</span></span>
    - <span data-ttu-id="72922-133">Ressource : Type</span><span class="sxs-lookup"><span data-stu-id="72922-133">Resource: Type</span></span>
    - <span data-ttu-id="72922-134">Sécurité : [Extension pour les UR OAuth](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="72922-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="72922-135">FembaVersion (notre code exige que l’on comprenne la version vers laquelle nous devons pivoter, car nous prise en charge les versions multiples).</span><span class="sxs-lookup"><span data-stu-id="72922-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="72922-136">Consultez [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="72922-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="72922-137">Patient</span><span class="sxs-lookup"><span data-stu-id="72922-137">Patient</span></span>

<span data-ttu-id="72922-138">Il s’agit des champs requis au minimum, qui sont un sous-ensemble des champs de profil [du patient Argot](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) :</span><span class="sxs-lookup"><span data-stu-id="72922-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="72922-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="72922-139">Name.Family</span></span>
 - <span data-ttu-id="72922-140">Name.Given</span><span class="sxs-lookup"><span data-stu-id="72922-140">Name.Given</span></span>
 - <span data-ttu-id="72922-141">Sexe</span><span class="sxs-lookup"><span data-stu-id="72922-141">Gender</span></span>
 - <span data-ttu-id="72922-142">Date BirthDate</span><span class="sxs-lookup"><span data-stu-id="72922-142">BirthDate</span></span>
 - <span data-ttu-id="72922-143">MRN (identificateur)</span><span class="sxs-lookup"><span data-stu-id="72922-143">MRN (Identifier)</span></span>

<span data-ttu-id="72922-144">Outre les champs Argot, pour une expérience utilisateur excellente, l’application Patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="72922-145">Name.Use</span><span class="sxs-lookup"><span data-stu-id="72922-145">Name.Use</span></span>
 - <span data-ttu-id="72922-146">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="72922-146">Name.Prefix</span></span>
 - <span data-ttu-id="72922-147">CareProvider (cette référence sur la ressource du patient doit inclure les champs d’affichage illustrés dans l’exemple suivant.)</span><span class="sxs-lookup"><span data-stu-id="72922-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="72922-148">Une recherche de ressources utilise la méthode POST à /Patient/_search et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="72922-149">id</span><span class="sxs-lookup"><span data-stu-id="72922-149">id</span></span>
 - <span data-ttu-id="72922-150">family:contains=(recherche tous les patients dont le nom de famille contient la valeur.)</span><span class="sxs-lookup"><span data-stu-id="72922-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="72922-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="72922-151">given=\<substring></span></span>
 - <span data-ttu-id="72922-152">name=\<substring></span><span class="sxs-lookup"><span data-stu-id="72922-152">name=\<substring></span></span>
 - <span data-ttu-id="72922-153">birthdate=(correspondance exacte)</span><span class="sxs-lookup"><span data-stu-id="72922-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="72922-154">\_nombre (nombre maximal de résultats à retourner)</span><span class="sxs-lookup"><span data-stu-id="72922-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="72922-155">La réponse doit contenir le nombre total d’enregistrements renvoyés suite à la recherche, et le nombre sera utilisé par l’App Patients pour limiter le nombre d’enregistrements \_ renvoyés.</span><span class="sxs-lookup"><span data-stu-id="72922-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="72922-156">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="72922-156">identifier=\<mrn></span></span>

<span data-ttu-id="72922-157">L’objectif est de pouvoir rechercher et filtrer un patient comme suit :</span><span class="sxs-lookup"><span data-stu-id="72922-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="72922-158">N° : il s’agit de l’ID de ressource dont dispose chaque ressource de l’affectation FEMBA.</span><span class="sxs-lookup"><span data-stu-id="72922-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="72922-159">MRN : il s’agit de l’identificateur réel du patient que le personnel clinique connaît.</span><span class="sxs-lookup"><span data-stu-id="72922-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="72922-160">Nous comprenons que cette fonction MRN est basée sur le type d’identificateur à l’intérieur de la ressource d’identificateur dans FEMBA</span><span class="sxs-lookup"><span data-stu-id="72922-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="72922-161">Nom</span><span class="sxs-lookup"><span data-stu-id="72922-161">Name</span></span>
- <span data-ttu-id="72922-162">Date de naissance</span><span class="sxs-lookup"><span data-stu-id="72922-162">Birthdate</span></span>

<span data-ttu-id="72922-163">Consultez l’exemple suivant de cet appel.</span><span class="sxs-lookup"><span data-stu-id="72922-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="72922-164">Consultez [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="72922-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="72922-165">Observation</span><span class="sxs-lookup"><span data-stu-id="72922-165">Observation</span></span>

<span data-ttu-id="72922-166">Voici les champs minimum requis, qui sont un sous-ensemble du profil des signes vital d’Argot :</span><span class="sxs-lookup"><span data-stu-id="72922-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="72922-167">Effectif (date ou période)</span><span class="sxs-lookup"><span data-stu-id="72922-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="72922-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="72922-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="72922-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="72922-169">ValueQuantity.Value</span></span>

<span data-ttu-id="72922-170">Outre les champs Argot, pour une expérience utilisateur excellente, l’application Patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="72922-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="72922-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="72922-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="72922-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="72922-173">Si vous utilisez des observations de composant, la même logique s’applique à chaque observation de composant.</span><span class="sxs-lookup"><span data-stu-id="72922-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="72922-174">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="72922-175">patient=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="72922-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="72922-176">sort:desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="72922-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="72922-177">L’objectif est de pouvoir récupérer les derniers signes essentiels d’un patient, [VitalSigns.DSTU.saz] (observation ?).</span><span class="sxs-lookup"><span data-stu-id="72922-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="72922-178">Consultez [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="72922-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="72922-179">Condition</span><span class="sxs-lookup"><span data-stu-id="72922-179">Condition</span></span>

<span data-ttu-id="72922-180">Voici les champs minimum requis, qui sont un sous-ensemble du profil [de condition Argot :](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)</span><span class="sxs-lookup"><span data-stu-id="72922-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="72922-181">Code.Coding[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="72922-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="72922-182">Outre les champs Argot, pour une grande expérience utilisateur, l’application Patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="72922-183">Date enregistrée</span><span class="sxs-lookup"><span data-stu-id="72922-183">Date Recorded</span></span>
 - <span data-ttu-id="72922-184">Gravité</span><span class="sxs-lookup"><span data-stu-id="72922-184">Severity</span></span>

<span data-ttu-id="72922-185">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="72922-186">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="72922-186">patient=\<patient id></span></span>
 - <span data-ttu-id="72922-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="72922-187">_count=\<max results></span></span>

<span data-ttu-id="72922-188">Consultez l’exemple suivant de cet appel :</span><span class="sxs-lookup"><span data-stu-id="72922-188">See the following example of this call:</span></span>

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

<span data-ttu-id="72922-189">Consultez [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="72922-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="72922-190">Rencontrer</span><span class="sxs-lookup"><span data-stu-id="72922-190">Encounter</span></span>

<span data-ttu-id="72922-191">Voici les champs minimum requis, qui sont un sous-ensemble des champs « must have » du profil US Core Encounter :</span><span class="sxs-lookup"><span data-stu-id="72922-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="72922-192">Statut</span><span class="sxs-lookup"><span data-stu-id="72922-192">Status</span></span>
 - <span data-ttu-id="72922-193">Tapez[0]. Codage[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="72922-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="72922-194">En outre, les champs suivants des champs « doivent prendre en charge » du profil US Core Encounter</span><span class="sxs-lookup"><span data-stu-id="72922-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="72922-195">Point.Début</span><span class="sxs-lookup"><span data-stu-id="72922-195">Period.Start</span></span>
 - <span data-ttu-id="72922-196">Emplacement[0]. Location.Display</span><span class="sxs-lookup"><span data-stu-id="72922-196">Location[0].Location.Display</span></span>

<span data-ttu-id="72922-197">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="72922-198">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="72922-198">patient=\<patient id></span></span>
 - <span data-ttu-id="72922-199">_sort:desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="72922-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="72922-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="72922-200">_count=\<max results></span></span>

<span data-ttu-id="72922-201">L’objectif est de pouvoir récupérer le dernier emplacement connu du patient.</span><span class="sxs-lookup"><span data-stu-id="72922-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="72922-202">Chaque rencontre fait référence à une ressource d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="72922-202">Each encounter references a location resource.</span></span> <span data-ttu-id="72922-203">La référence doit également inclure le champ d’affichage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="72922-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="72922-204">Consultez l’exemple suivant de cet appel.</span><span class="sxs-lookup"><span data-stu-id="72922-204">See the following example of this call.</span></span>

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

<span data-ttu-id="72922-205">Consultez [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="72922-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="72922-206">MondeYIntolerance</span><span class="sxs-lookup"><span data-stu-id="72922-206">AllergyIntolerance</span></span>

<span data-ttu-id="72922-207">Il s’agit des champs requis au minimum, qui sont un sous-ensemble du profil d’argotaïeIntolerance :</span><span class="sxs-lookup"><span data-stu-id="72922-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="72922-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="72922-208">Code.Text</span></span>
 - <span data-ttu-id="72922-209">Code.Coding[0]. Affichage</span><span class="sxs-lookup"><span data-stu-id="72922-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="72922-210">Statut</span><span class="sxs-lookup"><span data-stu-id="72922-210">Status</span></span>

<span data-ttu-id="72922-211">Outre les champs Argot, pour une expérience utilisateur excellente, l’application Patients lit également les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="72922-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="72922-212">RecordedDate</span></span>
 - <span data-ttu-id="72922-213">Note.Text</span><span class="sxs-lookup"><span data-stu-id="72922-213">Note.Text</span></span>
 - <span data-ttu-id="72922-214">Réaction[..]. Substance.Text</span><span class="sxs-lookup"><span data-stu-id="72922-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="72922-215">Réaction[..]. [.]. Texte</span><span class="sxs-lookup"><span data-stu-id="72922-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="72922-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="72922-216">Text.Div</span></span>

<span data-ttu-id="72922-217">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="72922-218">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="72922-218">Patient =  \<patient id></span></span>

<span data-ttu-id="72922-219">Consultez l’exemple suivant de cet appel :</span><span class="sxs-lookup"><span data-stu-id="72922-219">See the following example of this call:</span></span>

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

<span data-ttu-id="72922-220">Consultez [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="72922-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="72922-221">Ordre des médications</span><span class="sxs-lookup"><span data-stu-id="72922-221">Medication Order</span></span>

<span data-ttu-id="72922-222">Voici les champs minimaux requis, qui sont un sous-ensemble du profil Médicaux d’Argot :</span><span class="sxs-lookup"><span data-stu-id="72922-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="72922-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="72922-223">DateWritten</span></span>
 - <span data-ttu-id="72922-224">Enr.Affichage</span><span class="sxs-lookup"><span data-stu-id="72922-224">Prescriber.Display</span></span>
 - <span data-ttu-id="72922-225">Medication.Display (référence de cas)</span><span class="sxs-lookup"><span data-stu-id="72922-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="72922-226">Médication.texte (concept de cas)</span><span class="sxs-lookup"><span data-stu-id="72922-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="72922-227">Outre les champs Argot, pour une expérience utilisateur excellente, l’application Patients peut également lire les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="72922-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="72922-228">DateEnded</span></span>
 - <span data-ttu-id="72922-229">Onstruction.Text</span><span class="sxs-lookup"><span data-stu-id="72922-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="72922-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="72922-230">Text.Div</span></span>

<span data-ttu-id="72922-231">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="72922-232">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="72922-232">patient=\<patient id></span></span>
 - <span data-ttu-id="72922-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="72922-233">_count=\<max results></span></span>

<span data-ttu-id="72922-234">Consultez l’exemple suivant de cet appel :</span><span class="sxs-lookup"><span data-stu-id="72922-234">See the following example of this call:</span></span>

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

<span data-ttu-id="72922-235">Consultez [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="72922-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="72922-236">Couverture</span><span class="sxs-lookup"><span data-stu-id="72922-236">Coverage</span></span>

<span data-ttu-id="72922-237">Voici les champs minimum requis, et non couverts par les profils Us Core ou Argot :</span><span class="sxs-lookup"><span data-stu-id="72922-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="72922-238">Payor</span><span class="sxs-lookup"><span data-stu-id="72922-238">Payor</span></span>

<span data-ttu-id="72922-239">Une recherche de ressources utilise la méthode GET et les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="72922-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="72922-240">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="72922-240">patient=\<patient id></span></span>

<span data-ttu-id="72922-241">Consultez l’exemple suivant de cet appel :</span><span class="sxs-lookup"><span data-stu-id="72922-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="72922-242">Consultez [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="72922-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="72922-243">Lieu</span><span class="sxs-lookup"><span data-stu-id="72922-243">Location</span></span>

<span data-ttu-id="72922-244">Cette ressource n’est utilisée qu’en tant que référence sur la [ressource Rencontrer.](#encounter)</span><span class="sxs-lookup"><span data-stu-id="72922-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="72922-245">Consultez [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) d’autres informations sur ce jeu de champs.</span><span class="sxs-lookup"><span data-stu-id="72922-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
