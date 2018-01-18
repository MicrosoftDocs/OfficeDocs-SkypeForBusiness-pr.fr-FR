---
title: "Déplacement du fournisseur de conférence audio d’un utilisateur à Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Modifier votre Skype pour les utilisateurs professionnels à partir des fournisseurs de conférence audio de tiers (ACP) à un fournisseur de conférence à distance dans Microsoft. "
ms.openlocfilehash: 79697299ce2c3e3fa398150cd300e305ef0c672a
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="3d0ef-103">Déplacement du fournisseur de conférence audio d’un utilisateur à Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d0ef-103">Moving a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="3d0ef-104">Pour utiliser la conférence Audio dans Office 365 avec Skype pour les entreprises et les Teams de Microsoft, les utilisateurs de votre organisation doivent disposer d’une licence de **Conférence Audio** affectée ainsi que leur fournisseur de conférence audio doivent être définies à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an **Audio Conferencing** license assigned to them and their audio conferencing provider must be set to Microsoft.</span></span> <span data-ttu-id="3d0ef-105">Pour obtenir plus d’informations sur les licences et son coût, reportez-vous à la section [Essayez ou achetez audioconférence dans Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="3d0ef-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a><span data-ttu-id="3d0ef-106">Pour déplacer un fournisseur de conférence audio d’un utilisateur à Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d0ef-106">To move a user's audio conferencing provider to Microsoft</span></span>

<span data-ttu-id="3d0ef-107">Si une licence de **Conférence Audio** est affectée à un utilisateur qui ne possède pas un fournisseur de conférence audio, le fournisseur de l’utilisateur est automatiquement configurée à Microsoft et vous n’avez rien à faire.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-107">If an **Audio Conferencing** license is assigned to a user who doesn't have an audio conferencing provider, the user's provider will be automatically set to Microsoft and you don't have to do anything else.</span></span> <span data-ttu-id="3d0ef-108">Si l’utilisateur avait déjà un fournisseur de conférence audio, vous devez modifier le fournisseur de l’utilisateur à Microsoft après l’attribution d’une licence de **Conférence Audio** .</span><span class="sxs-lookup"><span data-stu-id="3d0ef-108">If the user already had an audio conferencing provider, you must change the user's provider to Microsoft after assigning them an **Audio Conferencing** license.</span></span>
  
<span data-ttu-id="3d0ef-109">Pour définir Microsoft comme le fournisseur de conférence audio pour un utilisateur qui dispose d’une licence de **Conférence Audio** affecté mais utilise un autre fournisseur de conférence audio, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3d0ef-109">To set Microsoft as the audio conferencing provider for a user that has an **Audio Conferencing** license assigned but is using another audio conferencing provider, do this:</span></span>
  
1. <span data-ttu-id="3d0ef-110">Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="3d0ef-111">Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-111">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="3d0ef-112">Dans le **Skype pour le centre d’administration Business**, passez à **l’audioconférence**.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-112">In the **Skype for Business admin center**, go to **Audio conferencing**.</span></span>
    
4. <span data-ttu-id="3d0ef-113">Si vous voyez une bannière qui vous avertit qu’il existe des utilisateurs qui ont une **Conférence Audio** licence affectés mais n’avez pas Microsoft défini comme leur fournisseur de conférence audio pour l’instant, cliquez sur **Cliquez ici pour les déplacer**.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="3d0ef-114">Si vous ne voyez pas la bannière, dans le **Skype pour le centre d’administration Business** cliquez sur **utilisateurs**et puis sélectionnez le filtre **prête à être déplacée à l’Audio conférence des utilisateurs** .</span><span class="sxs-lookup"><span data-stu-id="3d0ef-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
5. <span data-ttu-id="3d0ef-115">Sélectionnez les utilisateurs que vous souhaitez déplacer, puis dans le volet Actions, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-115">Select the users you want to move, and then in the Action pane, click **Edit**.</span></span>
    
6. <span data-ttu-id="3d0ef-116">Sélectionnez **Microsoft** dans la liste **nom du fournisseur** .</span><span class="sxs-lookup"><span data-stu-id="3d0ef-116">Select **Microsoft** in the **Provider name** list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3d0ef-117">Lorsque le fournisseur de conférence audio d’un utilisateur est modifié à Microsoft, les informations de conférence audio de l’utilisateur change.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-117">When the audio conferencing provider of a user is changed to Microsoft, the audio conferencing information of the user will change.</span></span> <span data-ttu-id="3d0ef-118">Si vous avez besoin de conserver ces informations, veuillez l’enregistrer ailleurs avant de modifier le fournisseur d’un des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-118">If you need to keep this information, please record it somewhere before changing the provider of any of the users.</span></span> 
  
7. <span data-ttu-id="3d0ef-119">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-119">Click **Save**.</span></span>
    
## <a name="what-else-should-i-know"></a><span data-ttu-id="3d0ef-120">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3d0ef-120">What else should I know?</span></span>

- <span data-ttu-id="3d0ef-121">Si vous sélectionnez l’utilisateur dans la liste, vous pouvez afficher les informations de conférence audio par défaut de l’utilisateur, mais vous ne pourrez pas voir la code PIN de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-121">If you select the user in the list, you can view the default audio conferencing information of the user but you won't be able to see the audio conferencing PIN.</span></span> <span data-ttu-id="3d0ef-122">Vous pouvez réinitialiser la code PIN d’un utilisateur de conférence audio en cliquant sur **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="3d0ef-122">You can reset the audio conferencing PIN of a user by clicking **Reset**.</span></span>
    
- <span data-ttu-id="3d0ef-123">Si vous souhaitez modifier les paramètres de conférence audio pour un utilisateur, vous pouvez sélectionnez l’utilisateur dans la liste puis cliquez sur **Modifier** et apportez vos modifications dans la page de **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="3d0ef-123">If you want to change audio conferencing settings for a user, you can select the user from the list and then click **Edit** and make your changes on the **Properties** page.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="3d0ef-124">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="3d0ef-124">Related topics</span></span>

[<span data-ttu-id="3d0ef-125">Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d0ef-125">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

