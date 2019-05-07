---
title: Vue d’ensemble des applications de patients
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
ms.openlocfilehash: 25eb1b4ee09eec8395db2ac821d19624a508c937
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643102"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a>Intégration de santé les enregistrements électroniques dans les équipes Microsoft

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Cet article est destiné à un développeur à l’aide des API FHIR par-dessus un système d’information médicale pour se connecter à Microsoft Teams intéressé par la santé générale. Cela permettrait des scénarios de coordination de soins qui répondent aux besoins d’une organisation de soins.

Cet article documents spécifications de l’interface FHIR pour l’application Microsoft équipes Patients et de présentation qui est requise pour la configuration d’un serveur FHIR et connexion à l’application de Patients dans votre environment\tenant de développement. Vous devez également être familiarisé avec la documentation du serveur FHIR que vous avez choisi, qui doit être une des options prises en charge :
- Datica (par le biais de son offre [CMI](https://datica.com/compliant-managed-integration/) )
- Informations Cloverleaf (à l’aide du [Pont FHIR d’informations](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))
- REDOX (par le biais de la [R ^ server FHIR](https://www.redoxengine.com/fhir/))
- Dapasoft (via [Corolar sur FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))

> [!NOTE]
> Ce processus ne pas inclut des étapes qui utilisent le centre d’administration de Microsoft Teams ou les applets de commande PowerShell pour activer les fonctionnalités. La configuration s’effectue entièrement sur le côté serveur et le service FHIR et dans le client app Patients.

Vous trouverez ci-dessous est l’architecture de l’application de Patients :

![Architecture d’application patients](../../media/patients-app-architecture.png)

Les sections suivantes expliquent les exigences de la couche d’accès aux données FHIR uniquement pour l’application de Patients qu’un serveur FHIR (ou EHR activé FHIR API) doit satisfaire afin d’intégrer à l’application de Patients, notamment les suivants :

- Attentes autour de l’authentification des utilisateurs
- Exigences fonctionnelles et techniques de l’interface de l’intégration
- Attentes autour de performances et la fiabilité
- Attentes autour de ressources FHIR à prendre en charge pour l’application de Patients
- Processus d’intégration et le modèle d’engagement attendu
- Comment vous inscrire et votre client dans l’aperçu de l’application de Patients privée
- Comment prendre en main FHIR et certains problèmes courants rencontrés avec l’application de Patients
- Besoins futurs de l’itération suivante de l’application de Patients

> [!NOTE]
> Dans les sections suivantes, le mot « partenaire » ou « interopérabilité » est utilisé pour faire référence à toute partie 3 organisation qui permet l’intégration aux systèmes EHR pour l’application de Patients via FHIR et est l’implémentation d’un serveur FHIR pour faire correspondre les spécifications répertoriées.

## <a name="functional-and-technical-requirements"></a>Exigences fonctionnelles et techniques  

### <a name="authentication"></a>Authentification  

Autorisation au niveau de l’application *sans prise en charge pour l’autorisation au niveau utilisateur* est le moyen plus couramment pris en charge pour effectuer des transformations de données et exposer des connexions aux données DMI via FHIR, même si le système EHR peut implémenter l’autorisation au niveau utilisateur . Le Service d’interopérabilité (partenaire) Obtient avec élévation de privilèges d’accès aux données DMI et qu’ils exposent les mêmes données que les ressources appropriées de FHIR aucun contexte d’autorisation transmis à l’utilisateur du Service Interop (l’application de Patients) intégrant l’interopérabilité Service ou une autre plateforme. L’application de Patients ne sera pas en mesure d’appliquer l’autorisation au niveau utilisateur, mais ne prend pas en charge une application à l’authentification entre l’application de Patients et de service du partenaire PIA.

Le modèle d’authentification pour une Application est décrite ci-dessous :

Service d’authentification du service de doit être effectuée par le biais de OAuth 2.0 [flux d’informations d’identification du Client](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/). Le service partenaire doit fournir les éléments suivants :

1. Le service partenaire permet à l’application de Patients créer un compte avec le partenaire, qui permet à l’application de Patients générer et identifiant_client propre et client_secret, géré par le biais d’un portail de l’enregistrement d’authentification sur le serveur du partenaire d’authentification.
2. Le service partenaire possède le système d’authentification/autorisation, qui accepte et vérifie (authentifie) le client fourni les informations d’identification et donne un jeton d’accès avec indication du client dans l’étendue, comme décrit ci-dessous.
3. Pour des raisons de sécurité ou en cas de violation de la clé secrète, l’application de Patients permettre générer de nouveau la clé secrète et invalider ou supprimer l’ancien secret (le même exemple est disponible dans Azure Portal - inscription de l’application DAS)
4. Le point de terminaison de métadonnées qui héberge la déclaration de conformité doit être non authentifié, il doit être accessible sans jeton d’authentification.
5. Le service de partenaire fournit le point de terminaison jeton pour l’application de Patients demander un jeton d’accès à l’aide d’un flux d’informations d’identification de client. L’url comme serveur d’autorisation jeton doit faire partie de la déclaration de conformité (capacité) FHIR extraite de métadonnées sur le serveur FHIR comme dans cet exemple :

![Application de patients 5](../../media/Patient-app-5.png)

Une demande pour un jeton d’accès se compose des paramètres suivants :

    POST /token HTTP/1.1
    Host: authorization-server.com

    grant-type=client_credentials
    &client_id=xxxxxxxxxx
    &client_secret=xxxxxxxxxx

Le service de partenaire fournit les identifiant_client client_secret pour application de Patients, gérée par le biais d’un portail de l’enregistrement d’authentification côté du partenaire. Le service de partenaire fournit le point de terminaison du jeton de demande l’accès à l’aide d’un flux d’informations d’identification de client. Une réponse positive doit inclure les paramètres token_type, access_token et expires_in.

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a>Routage : Mappage DAS client au point de terminaison fournisseur

L’application de Patients se connecte à un service de partenaires via un seul point de terminaison. Le service partenaire possède et gère un mécanisme pour mapper chaque client Microsoft (ID de client DAS) à un fournisseur de santé respectif (server FHIR) qui fonctionne avec le service partenaire.

Mappage du client DAS à un point de terminaison fournisseur utilise l’ID de client DAS (GUID). L’application de Patients transmet l’ID de client dans la portée, lors de la demande un jeton d’accès pour chaque demande. Le service partenaire conserve le mappage de l’ID de client au point de terminaison fournisseur et redirige les demandes vers un point de terminaison fournisseur en fonction de l’ID de client. Pour ce faire, le partenaire prend en charge la configuration à leur extrémité (manuellement ou via un portail dans le cadre de l’intégration des organisations fournisseur vers leur plateforme Interop).

Le flux de travail d’authentification et de routage est donné ci-dessous :

![Application de patients 6](../../media/Patient-app-6.png)

1. Demande de jeton d’accès application en envoyant :
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. Répondre avec un jeton d’application :

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. Demander des données protégées avec un jeton d’accès.
4. Message d’autorisation : sélectionnez le serveur FHIR approprié à acheminer vers à partir de l’ID de client dans une étendue
5. Envoie les données d’application protégée à partir du serveur FHIR autorisé après l’authentification avec le jeton d’application.

## <a name="interfaces"></a>Interfaces

Appels spécifiques et les champs utilisés par l’application de Patients sont décrits dans les articles suivants. Sélectionnez l’interface applicable à votre serveur/FHIR FHIR API.

- [Spécification d’interface DSTU2](dstu2-interface.md)
- [Spécification d’interface STU3](stu3-interface.md)

## <a name="performance-and-reliability"></a>Performances et la fiabilité

Alors que l’application de Patients est en mode Aperçu privé, il n’existe aucune garantie sur les performances de bout en bout. Facteurs de performances sont les latences relatives de tronçons impliqués dans le flux de travail, en commençant à partir de ce dossier dans l’environnement du système d’intégrité, à l’interopérabilité partenaire et leurs infra, y compris le serveur FHIR et horizontalement à l’écosystème d’Office 365 et Application des patients.

![Partenaires d’interopérabilité de base](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a>Mise en route FHIR  

Si vous ne connaissez FHIR et ont besoin d’accéder facilement à un serveur FHIR que vous pouvez exposer à l’interface de l’intégration Microsoft équipes EHR, Microsoft possède un serveur de la FHIR open source disponible pour tous les développeurs à utiliser. Consultez l’article [What ' s FHIR Server pour Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) pour en savoir plus sur open source Server FHIR disponibles auprès de Microsoft et le déployer pour vos organisations.

Vous pouvez également utiliser l’environnement de EHR sandbox HSPC ouvrir pour créer un un DMI qui prend en charge un serveur FHIR open également et d’utiliser cette option pour utiliser l’application de Patients. Nous vous recommandons de lire la [documentation HSPC en bac à sable](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox). Non seulement le bac à sable fournit une interface utilisateur orientée et façon conviviale de création, ajout et modification des Patients, il vous fournit également quelques exemples pour commencer.  

## <a name="enroll-in-the-private-preview"></a>S’inscrire à l’aperçu privée

Une fois que vous avez créé l’open source Server FHIR, il est très facile de se connecter à l’application de Patients à l’intérieur de votre client en suivant les étapes mentionnées ci-dessous :

1. [Nous contacter](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) avec les informations initiales suivantes :  
    - Votre nom 
    - Votre Position, 
    - La société ou l’organisation que vous déclarez
    - Pourquoi vous êtes intéressé par l’application de Patients pour l’intégration DMI. 

    Nous y revenir vous dès que possible avec d’autres questions et vous guide dans un processus pour obtenir le programme d’installation pour l’aperçu privé.

2. Assurez-vous que chargement de version test de custom applications est activée sur le client où vous allez tester l’application de Patients. Reportez-vous aux [stratégies d’autorisation application](../../admin-settings.md) pour découvrir comment activer à partir du centre d’administration des équipes pour le client de votre client.

3. Sideload l’application de Patients manifeste que vous obtenez à partir de Microsoft (une fois que nous traitons votre courrier électronique pour nous) dans une équipe dans le client qui doit être utilisé pour la coordination soins et patients scénarios arrondis. Obtenir des instructions détaillées autour de procédure côté-charge une application se trouvent dans [télécharger un package d’application pour les équipes Microsoft](/microsoftteams/platform/concepts/apps/apps-upload)

4. Accédez à la chaîne générale en tant que propriétaire de l’équipe, puis sur l’onglet Patients. Vous devez voir une expérience première exécution présente deux options c'est-à-dire EHR Mode et Mode manuel. Sélectionnez le **mode DMI** et copier le point de terminaison FHIR Server (que vous avez simplement le programme d’installation précédemment avec toutes les données requises et les ressources par les spécifications ci-dessus) dans le champ de lien et donnez un nom qui représente également le serveur FHIR à la connexion. Cliquez sur se connecter, et tous les éléments doivent être prêt à l’emploi.

    ![Paramètres du serveur app patients](../../media/patients-server.png)

5. Démarrez à l’aide de l’application pour rechercher à partir de ce serveur/dossier FHIR des Patients et les ajouter à une liste et Veuillez vous [donnez vos commentaires](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) si quelque chose ne fonctionne pas. En outre, pour établir une version de l’application de Patients entièrement authentifiée-> flux FHIR Server, prendre part, dans la boîte de dialogue en mode hors connexion avec Microsoft Teams d’ingénierie produit prestataires, par le biais de mentionné la demande du courrier électronique afin de clarifier les exigences et nous allons aider à autoriser cette opération pour vous par les exigences d’authentification décrites ci-dessus dans le document FHIR Interface.  


