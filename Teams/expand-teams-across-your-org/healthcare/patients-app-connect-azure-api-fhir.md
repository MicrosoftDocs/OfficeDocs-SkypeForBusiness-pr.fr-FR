---
title: Connecter l’application coordination des soins à l’API Azure pour FHIR
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment connecter l’application patients dans Microsoft teams à l’API Azure pour FHIR (ressources d’interopérabilité Fast Healthcare).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e3ff2f42953d59d1eecbc96179759f2ad9024f82
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772255"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="9e3ec-103">Connecter l’application coordination des soins à l’API Azure pour FHIR</span><span class="sxs-lookup"><span data-stu-id="9e3ec-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="9e3ec-104">À compter du 30 octobre 2020, l’application patients a été supprimée et remplacée par l' [application listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="9e3ec-105">Dans le cas des listes, les équipes de soins de votre organisation peuvent créer des listes de patients dans le cas de signes et de réunions d’équipe de manière générale.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="9e3ec-106">Consultez le modèle patients dans les listes pour commencer.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="9e3ec-107">Pour en savoir plus sur la gestion de l’application listes dans votre organisation, voir [gérer l’application listes](../../manage-lists-app.md) .</span><span class="sxs-lookup"><span data-stu-id="9e3ec-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="9e3ec-108">Suivez ces étapes pour autoriser l’application patients dans Microsoft teams à accéder à une API Azure pour l’instance FHIR.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-108">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="9e3ec-109">Cet article part du principe que vous disposez d’une [API Azure pour](https://azure.microsoft.com/services/azure-api-for-fhir/) la configuration de l’instance FHIR et qu’elle est configurée dans votre client.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-109">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="9e3ec-110">Si vous n’avez pas encore créé d’API Azure pour FHIR dans votre client, reportez-vous à [démarrage rapide : déployer l’API Azure pour FHIR à l’aide d’Azure Portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span><span class="sxs-lookup"><span data-stu-id="9e3ec-110">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="9e3ec-111">Cliquez [ici](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) pour accorder l’autorisation d’administrateur pour l’application patients.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-111">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="9e3ec-112">Lorsque vous y êtes invité, connectez-vous à l’aide de vos informations d’identification d’administrateur client ou d’administrateur général, puis cliquez sur **accepter** pour accorder les autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-112">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Capture d’écran de la demande d’autorisation pour l’application patients](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="9e3ec-114">Fermez la fenêtre après l’avoir acceptée.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-114">After you accept, close the window.</span></span> <span data-ttu-id="9e3ec-115">Une page peut ressembler à ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-115">You'll see a page that may look like this.</span></span> <span data-ttu-id="9e3ec-116">Vous pouvez ignorer le message d’erreur sur la page.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-116">You can ignore the error message on the page.</span></span> <span data-ttu-id="9e3ec-117">C’est inoffensif et indique que cette autorisation est accordée.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-117">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="9e3ec-118">(Nous travaillons actuellement sur une page plus conviviale pour cette URL.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-118">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="9e3ec-119">Restez informé !)</span><span class="sxs-lookup"><span data-stu-id="9e3ec-119">Stay tuned!)</span></span>

    ![Capture d’écran d’une demande d’autorisation pour l’application patients](../../media/patients-app-permissions-request-granted.png)
    
2. <span data-ttu-id="9e3ec-121">Connectez-vous au [portail Azure](https://portal.azure.com) à l’aide de vos informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-121">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="9e3ec-122">Dans le volet de navigation de gauche, cliquez sur **Azure Active Directory** , puis sélectionnez **applications d’entreprise** .</span><span class="sxs-lookup"><span data-stu-id="9e3ec-122">In the left navigation, select **Azure Active Directory** , and then select **Enterprise Applications** .</span></span>

    <span data-ttu-id="9e3ec-123">Recherchez une ligne nommée **patients (dev)** , puis copiez la valeur de la colonne **ID d’objet** dans le presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-123">Look for a row named **Patients (dev)** , and then copy the value in the **Object ID** column to your clipboard.</span></span>
    
    ![Capture d’écran de la ligne patients (dev) dans Azure Portal](../../media/patients-app-azure-portal-object-id.png)
    
4. <span data-ttu-id="9e3ec-125">Accédez à l’instance d’API Azure pour FHIR à laquelle vous voulez connecter l’application patients (en effectuant une recherche ou en naviguant dans vos ressources), puis ouvrez les paramètres de cette instance.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-125">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Capture d’écran de l’API Azure pour les paramètres d’instance FHIR dans Azure Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="9e3ec-127">Cliquez sur **authentification** , puis collez l’ID d’objet que vous avez copié à l’étape 3 dans la zone **ID d’objet autorisés** .</span><span class="sxs-lookup"><span data-stu-id="9e3ec-127">Click **Authentication** , and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="9e3ec-128">Cela permet à l’application patients d’accéder au serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-128">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="9e3ec-129">Après avoir collé l’ID d’objet, Azure Active Directory le valide et une coche verte apparaît à côté de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-129">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Capture d’écran des paramètres d’authentification dans le portail Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="9e3ec-131">Cliquez sur **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="9e3ec-131">Click **Save** .</span></span> <span data-ttu-id="9e3ec-132">Cette opération redéploie l’instance, qui peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-132">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="9e3ec-133">Cliquez sur **vue d’ensemble** , puis copiez l’URL à partir du **point de terminaison de métadonnées FHIR** .</span><span class="sxs-lookup"><span data-stu-id="9e3ec-133">Click **Overview** , and then copy the URL from **FHIR metadata endpoint** .</span></span> <span data-ttu-id="9e3ec-134">Supprimez la balise Metadata pour obtenir l’URL du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-134">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="9e3ec-135">Par exemple, https://test02-teamshealth.azurehealthcareapis.com/ .</span><span class="sxs-lookup"><span data-stu-id="9e3ec-135">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Capture d’écran du point de terminaison de métadonnées dans Azure Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="9e3ec-137">Dans Teams, accédez à l’instance d’application patients qui est chargée dans votre équipe, cliquez sur **paramètres** , puis dans la zone **lien** , entrez l’URL du point de terminaison du serveur FHIR.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-137">In Teams, go to the Patients app instance that's loaded in your team, click **Settings** , and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="9e3ec-138">Cliquez ensuite sur **connexion** pour établir une connexion et Rechercher et ajouter des patients à votre liste.</span><span class="sxs-lookup"><span data-stu-id="9e3ec-138">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Capture d’écran des paramètres de l’application patients dans teams](../../media/patients-app-teams.png)
    
    <span data-ttu-id="9e3ec-140">Si vous obtenez un message d’erreur lors de la connexion à teams au cours de cette étape, vous pouvez envoyer une capture d’écran détaillée de l’erreur, des journaux de [Fiddler](https://www.telerik.com/download/fiddler) et de toutes les autres étapes de reproduction dans un courrier électronique avec une ligne d’objet de «application patients – résolution de EMR en mode [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9e3ec-140">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9e3ec-141">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="9e3ec-141">Related topics</span></span>

- [<span data-ttu-id="9e3ec-142">Présentation de l’application Patients</span><span class="sxs-lookup"><span data-stu-id="9e3ec-142">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="9e3ec-143">Intégration des dossiers médicaux électroniques dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e3ec-143">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
