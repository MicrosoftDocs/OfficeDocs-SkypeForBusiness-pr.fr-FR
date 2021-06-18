---
title: Présentation de l’application Patients
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
description: Découvrez comment intégrer des enregistrements médicaux électroniques dans l’application Patients de Microsoft Teams à l’aide d’API FEMBA.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2b4878f67b7738a13e3c1385ee0713d6e3e3d481
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096208"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Intégration des dossiers médicaux électroniques dans Microsoft Teams

> [!NOTE]
> À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui soutien l’équipe. Toutes les données associées à l’application Patients sont conservées dans ce groupe mais ne sont plus accessibles via l’interface utilisateur. Les utilisateurs peuvent re-créer leurs listes à l’aide de l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Les listes permet aux équipes de soins de votre organisation de santé de créer des listes de patients pour différents scénarios (arrondis, réunions d’équipe de formation, surveillance générale des patients, etc.). Pour commencer, consultez le modèle Patients dans listes. Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, consultez [Gérer l’application Listes](../../manage-lists-app.md).

Cet article est destiné à un développeur informatique de santé général intéressé par l’utilisation d’API FEMBA sur la base d’un système d’informations médicales pour se connecter à Microsoft Teams. Cela permettra des scénarios de coordination des soins qui correspondent aux besoins d’une organisation de soins de santé.

Les articles liés documentent les spécifications de l’interface FEMBA pour l’application Patients de Microsoft Teams, et les sections suivantes expliquent ce qui est nécessaire pour la configuration d’un serveur FEMBA et la connexion à l’application Patients dans votre environnement de développement ou client. Vous devez également être familiarisé avec la documentation du serveur F INF que vous avez choisi, laquelle doit être l’une des options prise en charge :

- Datica (via son [offre CMI)](https://datica.com/compliant-managed-integration/)
- Infor Premierrleaf (via le [pont Infor FEMBA)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)
- Red mail (via le [serveur R^FEMBA)](https://www.redoxengine.com/fhir/)
- Microsoft (par le biais [de Corolar sur FEMBA)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)

> [!NOTE]
> Ce processus n’inclut pas les étapes qui utilisent le Centre d’administration Microsoft Teams ou les cmdlets PowerShell pour activer les fonctionnalités. La configuration est entièrement effectuée sur le côté serveur/service FEMBA et dans le client de l’application Patients.

Voici l’architecture de l’application Patients illustrée ci-dessous :

![Diagramme de l’architecture de l’application Patients](../../media/patients-app-architecture.png)

Les sections suivantes expliquent les conditions requises de la couche d’accès aux données uniquement pour l’application Patients qu’un serveur FEMBA (ou API F INP activé pour l’utilisation d’un nom de groupe) doit respecter pour s’intégrer à l’application Patients, notamment les suivantes :

- Attentes en matière d’authentification des utilisateurs
- Exigences fonctionnelles et techniques de l’interface d’intégration
- Attentes en matière de performances et de fiabilité
- Attentes autour des ressources de l’FEMBA à prendre en charge pour l’application Patients
- Processus d’intégration et modèle d’engagement attendu
- Mise en place de la FEMBA et problèmes courants rencontrés avec l’application Patients
- Conditions requises pour la prochaine itération de l’application Patients

> [!NOTE]
> Dans les sections suivantes, le terme « partenaire » ou « partenaire Interop » est utilisé pour faire référence à n’importe quelle organisation tierce qui autorise l’intégration aux systèmes EHR pour l’application Patients via FEMBA et implémente un serveur FEMBA pour qu’il corresponde aux spécifications répertoriées.

## <a name="functional-and-technical-requirements"></a>Exigences fonctionnelles et techniques  

### <a name="authentication"></a>Authentification  

L’autorisation  au niveau de l’application sans prise en charge de l’autorisation au niveau utilisateur est le moyen le plus couramment pris en charge pour effectuer des transformations de données et exposer les connexions aux données d’un réseau d’entreprise via FEMBA, même si le système EHR peut implémenter l’autorisation au niveau utilisateur. Le partenaire Interop Service obtient un accès élevé aux données EHR et, lorsqu’ils exposent les mêmes données que les ressources FEMBA appropriées, aucun contexte d’autorisation n’est transmis à la clientèle de services Interop (l’application Patients) intégrée au service ou à la plateforme Interop. L’application Patients ne pourra pas appliquer l’autorisation au niveau utilisateur, mais prend en charge l’authentification des applications pour l’authentification des applications entre l’application Patients et le service du partenaire Interop.

Le modèle d’authentification d’application à application est décrit ci-dessous :

L’authentification de service à service doit être effectuée via le flux d’informations d’identification du [client](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)OAuth 2.0. Le service partenaire doit fournir les services suivants :

1. Le service partenaire permet à l’application Patients de créer un compte avec le partenaire, ce qui permet à l’application Patients de générer et de posséder des client_secret et client_id, gérés via un portail d’inscription d’authentification sur le serveur d’authentification du partenaire.

2. Le service partenaire est propriétaire du système d’authentification/autorisation, qui accepte et vérifie (authentifier) les informations d’identification client fournies et donne un jeton d’accès avec l’indication du client dans l’étendue, comme décrit ci-dessous.

3. Pour des raisons de sécurité ou en cas de violation secrète, l’application Patients peut générer à nouveau l’information secrète et invalider ou supprimer l’ancien secret (des exemples identiques sont disponibles dans le portail Azure - Inscription d’application AAD).

4. Le point de terminaison de métadonnées hébergeant l’instruction de conformité doit être non authentifié, il doit être accessible sans jeton d’authentification.

5. Le service partenaire fournit le point de terminaison de jeton pour l’application Patients afin de demander un jeton d’accès à l’aide d’un flux d’informations d’identification client. L’URL de jeton conformément au serveur d’autorisation doit faire partie de l’instruction de conformité (fonctionnalité) FEMBA récupérée à partir des métadonnées sur le serveur F INF, comme dans l’exemple ci-après :

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

Une demande de jeton d’accès se compose des paramètres suivants :

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

Le service partenaire fournit les client_id et client_secret Patients, gérées via un portail d’inscription d’erth du côté du partenaire. Le service partenaire fournit le point de terminaison pour demander un jeton d’accès à l’aide d’un flux d’informations d’identification client. Une réponse réussie doit inclure les paramètres token_type, access_token et expires_in réponses.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Routage : mappage du client AAD au point de terminaison fournisseur

L’application Patients se connecte à un service partenaire via un seul point de terminaison. Le service partenaire est le propriétaire et le maintien d’un mécanisme permettant d’associer chaque client Microsoft (ID de client AAD) à un fournisseur de soins de santé (FEMBA) approprié avec qui le service partenaire travaille.

Le mappage du client AAD à un point de terminaison de fournisseur utilise l’ID de locataire AAD (GUID). L’application Patients transmet l’ID de locataire dans l’étendue, lors de la demande d’un jeton d’accès pour chaque demande. Le service partenaire conserve le mappage de l’ID de locataire avec le point de terminaison du fournisseur et redirige les demandes vers un point de terminaison de fournisseur en fonction de l’ID de locataire. Pour ce faire, le partenaire prend en charge la configuration de son côté (manuellement ou via un portail dans le cadre de l’intégration des organisations du fournisseur à leur plateforme Interop).

Le flux de travail d’authentification et de routage s’affiche ci-dessous :

![Diagramme du flux de travail d’authentification et de routage](../../media/Patient-app-6.png)

1. Demandez le jeton d’accès à l’application en envoyant :
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. Répondre avec un jeton d’application :

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. Demander des données protégées avec un jeton Access.

4. Message d’autorisation : sélectionnez le serveur FEMBA approprié vers qui router à partir de l’ID de client dans l’étendue.

5. Envoie les données protégées par l’application à partir du serveur FEMBA autorisé après l’authentification avec le jeton d’application.

## <a name="interfaces"></a>Interfaces

Des appels et des champs spécifiques utilisés par l’application Patients sont documentés dans les articles suivants. Sélectionnez l’interface applicable à votre serveur FEMBA/API FEMBA.

- [Spécification de l’interface DSTU2](dstu2-interface.md)
- [Spécification de l’interface STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Performances et fiabilité

Si l’application Patients est en prévisualisation privée, il n’y a aucune garantie pour les performances de bout en bout. Les facteurs de performances comprennent les latencies relatives de tous les sauts impliqués dans le flux de travail, à partir de la gestion de la sécurité sociale dans l’environnement du système d’santé, au partenaire Interop et à son infrastructure, notamment le serveur FEMBA, puis à l’écosystème d’Office 365 et à l’application Patients.

![Illustration des performances des partenaires Interop](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Commencer à travailler avec FEMBA  

Si vous débutez avec FEMBA et que vous avez besoin d’un accès facile à un serveur FEMBA que vous pouvez exposer à l’interface d’intégration EHR de Microsoft Teams, Microsoft dispose d’un serveur FEMBA open source disponible pour tous les développeurs. Consultez [l’article](/azure/healthcare-apis/overview-open-source-server) Qu’est-ce que FEMBA Server pour Azure ? Pour en savoir plus sur le serveur open source FEMBA disponible auprès de Microsoft et le déployer pour votre organisation.

Vous pouvez également utiliser l’environnement EHR de bac à sable ouvert HSPC pour créer un ehr qui prend également en charge un serveur FPV ouvert et l’utiliser pour jouer avec l’application Patients. Nous vous recommandons de lire la documentation en bac à sable [HSPC.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox) Non seulement le bac à sable fournit-il un moyen simple, orienté IU et convivial de créer, d’ajouter et de modifier Patients, mais également de vous fournir plusieurs exemples pour commencer.