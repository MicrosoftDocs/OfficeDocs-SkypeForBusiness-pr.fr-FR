---
title: Connecter l’application coordination des soins à l’API Azure pour FHIR
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Découvrez comment connecter l’application Patients de Microsoft Teams à l’API Azure pour FEMBA (Fast Healthcare Interoperability Resources).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e41b071ef1724043f45c3783b062108d29a5190
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731152"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="f47dc-103">Connecter l’application coordination des soins à l’API Azure pour FHIR</span><span class="sxs-lookup"><span data-stu-id="f47dc-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="f47dc-104">À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’application [Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams.</span><span class="sxs-lookup"><span data-stu-id="f47dc-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="f47dc-105">Les données de l’application Patients sont stockées dans la boîte aux lettres de groupe du groupe Office 365 qui constitue le fond de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="f47dc-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="f47dc-106">Toutes les données associées à l’application Patients sont conservées dans ce groupe, mais ne peuvent plus être accessibles via l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f47dc-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="f47dc-107">Les utilisateurs peuvent re-créer leurs listes à l’aide de [l’application Listes.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="f47dc-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="f47dc-108">Avec les listes, les équipes de soins de votre organisation de soins de santé peuvent créer des listes de patients pour des scénarios allant des arrondis et des réunions d’équipe de recherche à la surveillance générale des patients.</span><span class="sxs-lookup"><span data-stu-id="f47dc-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="f47dc-109">Consultez le modèle Patients dans Listes pour commencer.</span><span class="sxs-lookup"><span data-stu-id="f47dc-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="f47dc-110">Pour en savoir plus sur la gestion de l’application Listes dans votre organisation, voir [l’application Gérer les listes.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="f47dc-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="f47dc-111">Suivez ces étapes pour autoriser l’application Patients de Microsoft Teams à accéder à une API Azure pour une instance FEMBA.</span><span class="sxs-lookup"><span data-stu-id="f47dc-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="f47dc-112">Cet article part du principe qu’une api Azure pour [une instance FEMBA](https://azure.microsoft.com/services/azure-api-for-fhir/) est configurée et configurée dans votre client.</span><span class="sxs-lookup"><span data-stu-id="f47dc-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="f47dc-113">Si vous n’avez pas encore créé d’instance d’API Azure pour FEMBA dans votre client, voir Démarrage rapide : Déployer [l’API Azure](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)pour FEMBA à l’aide du portail Azure.</span><span class="sxs-lookup"><span data-stu-id="f47dc-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="f47dc-114">Cliquez [ici pour](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) accorder le consentement de l’administrateur à l’application Patients.</span><span class="sxs-lookup"><span data-stu-id="f47dc-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="f47dc-115">À l’invite, connectez-vous à l’aide de  vos informations d’identification d’administrateur client ou d’administrateur global, puis cliquez sur Accepter pour accorder les autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="f47dc-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Capture d’écran de la demande d’autorisation pour l’application Patients](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="f47dc-117">Une fois l’acceptation acceptée, fermez la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="f47dc-117">After you accept, close the window.</span></span> <span data-ttu-id="f47dc-118">Vous verrez une page qui peut ressembler à ceci.</span><span class="sxs-lookup"><span data-stu-id="f47dc-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="f47dc-119">Vous pouvez ignorer le message d’erreur sur la page.</span><span class="sxs-lookup"><span data-stu-id="f47dc-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="f47dc-120">Il n’est pas dangereux et indique que le consentement est accordé.</span><span class="sxs-lookup"><span data-stu-id="f47dc-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="f47dc-121">(Nous travaillons à une page plus conviviale pour cette URL.</span><span class="sxs-lookup"><span data-stu-id="f47dc-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="f47dc-122">Restez connecté !)</span><span class="sxs-lookup"><span data-stu-id="f47dc-122">Stay tuned!)</span></span>

    ![Capture d’écran de la demande d’autorisation pour l’application Patients](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="f47dc-124">Connectez-vous au [portail Azure avec](https://portal.azure.com) vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f47dc-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="f47dc-125">Dans le dossier de navigation de gauche, sélectionnez **Azure Active Directory,** puis **Applications d’entreprise.**</span><span class="sxs-lookup"><span data-stu-id="f47dc-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="f47dc-126">Recherchez une ligne nommée **Patients (dev),** puis copiez la valeur de la colonne **ID** d’objet dans votre Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="f47dc-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Capture d’écran de la ligne Patients (dev) dans le portail Azure](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="f47dc-128">Allez à l’instance de ressource Api Azure pour FEMBA à laquelle vous voulez connecter l’application Patients (en la recherchant ou en parcourant vos ressources), puis ouvrez les paramètres pour cette instance.</span><span class="sxs-lookup"><span data-stu-id="f47dc-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Capture d’écran des paramètres d’instance de l’API Azure pour FEMBA dans le portail Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="f47dc-130">Cliquez **sur** Authentification, puis collez l’ID d’objet copié à l’étape 3 dans la zone **ID d’objet** autorisé.</span><span class="sxs-lookup"><span data-stu-id="f47dc-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="f47dc-131">Cela permet à l’application Patients d’accéder au serveur FEMBA.</span><span class="sxs-lookup"><span data-stu-id="f47dc-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="f47dc-132">Une fois que vous avez collé l’ID d’objet, Azure Active Directory la valide et une coche verte apparaît en regard de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="f47dc-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Capture d’écran des paramètres d’authentification dans le portail Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="f47dc-134">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f47dc-134">Click **Save**.</span></span> <span data-ttu-id="f47dc-135">Cela redéployer l’instance, ce qui peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="f47dc-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="f47dc-136">Cliquez sur **Vue d’ensemble,** puis copiez l’URL à partir du point de terminaison des **métadonnées FEMBA.**</span><span class="sxs-lookup"><span data-stu-id="f47dc-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="f47dc-137">Supprimez la balise de métadonnées pour obtenir l’URL du serveur FEMBA.</span><span class="sxs-lookup"><span data-stu-id="f47dc-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="f47dc-138">Par exemple, `https://test02-teamshealth.azurehealthcareapis.com/` .</span><span class="sxs-lookup"><span data-stu-id="f47dc-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![Point de terminaison des métadonnées dans le portail Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="f47dc-140">Dans Teams, allez à l’instance de l’application Patients chargée dans  votre équipe, cliquez sur **Paramètres,** puis dans la zone Lien, entrez l’URL du point de terminaison du serveur FEMBA.</span><span class="sxs-lookup"><span data-stu-id="f47dc-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="f47dc-141">Cliquez ensuite sur **Connexion pour** établir une connexion et rechercher et ajouter des patients à votre liste.</span><span class="sxs-lookup"><span data-stu-id="f47dc-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="f47dc-142">Paramètres de l’application Patients dans Teams</span><span class="sxs-lookup"><span data-stu-id="f47dc-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="f47dc-143">Si vous obtenez une erreur lors de la connexion à Teams au cours de cette étape, envoyez une capture d’écran détaillée de l’erreur, les journaux de [Fiddler](https://www.telerik.com/download/fiddler) et toute autre étape de reprotégation dans un e-mail avec la ligne d’objet « Application Patients - Mode EMR résolution des problèmes » à [teamsforhealthcare@service.microsoft.com.](mailto:teamsforhealthcare@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f47dc-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f47dc-144">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="f47dc-144">Related topics</span></span>

- [<span data-ttu-id="f47dc-145">Présentation de l’application Patients</span><span class="sxs-lookup"><span data-stu-id="f47dc-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="f47dc-146">Intégration des dossiers médicaux électroniques dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f47dc-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
