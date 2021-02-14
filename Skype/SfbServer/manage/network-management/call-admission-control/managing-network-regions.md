---
title: Gestion des régions réseau
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La région réseau* sont les concentrateurs réseau ou les dorsales utilisées dans la configuration du contrôle d’admission des appels, du système E9-1-1 et du contournement de média.
ms.openlocfilehash: 14c8004ddd14c0a37c25d700edae845ac9adfe29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816414"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="ade9d-103">Gestion des régions réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ade9d-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="ade9d-104">Les *régions réseau* sont les concentrateurs de réseau ou les dorsales principales utilisés dans la configuration du contrôle d’admission d’appels, E9-1-1, et la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="ade9d-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="ade9d-105">Utilisez les procédures suivantes pour afficher, créer ou modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="ade9d-106">Par exemple, si vous avez déjà créé des régions réseau pour une fonction vocale, vous n’avez pas besoin de créer de nouvelles régions réseau ; les autres fonctions Enterprise Voice avancées utiliseront ces mêmes régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="ade9d-107">Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ade9d-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="ade9d-108">Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis déployez ensuite le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central.</span><span class="sxs-lookup"><span data-stu-id="ade9d-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="ade9d-109">Utilisez les procédures de cet article pour afficher les informations de région réseau ou créer, modifier ou supprimer des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="ade9d-110">Afficher les informations de région réseau</span><span class="sxs-lookup"><span data-stu-id="ade9d-110">View network region information</span></span> 


<span data-ttu-id="ade9d-111">Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="ade9d-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ade9d-112">Chaque région réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="ade9d-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ade9d-113">Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute.</span><span class="sxs-lookup"><span data-stu-id="ade9d-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ade9d-114">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour afficher les régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="ade9d-115">Les régions réseau incluent des paramètres qui déterminent si d’autres chemins via Internet peuvent être empruntés pour les connexions audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="ade9d-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ade9d-116">Utilisez cette rubrique pour afficher des régions réseau existantes.</span><span class="sxs-lookup"><span data-stu-id="ade9d-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="ade9d-117">Pour afficher des informations sur une région réseau avec le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ade9d-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ade9d-118">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ade9d-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ade9d-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ade9d-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ade9d-120">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Région.**</span><span class="sxs-lookup"><span data-stu-id="ade9d-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ade9d-121">Dans la page **Région**, cliquez sur la région que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="ade9d-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="ade9d-122">Vous ne pouvez afficher qu’une région à la fois.</span><span class="sxs-lookup"><span data-stu-id="ade9d-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="ade9d-123">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ade9d-124">Affichage des informations de région réseau à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="ade9d-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ade9d-125">Vous pouvez afficher les informations de région réseau à l’Windows PowerShell et à l’aide de l’cmdlet **Get-CsNetworkRegion.**</span><span class="sxs-lookup"><span data-stu-id="ade9d-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="ade9d-126">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ade9d-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="ade9d-127">Pour afficher les informations de région réseau</span><span class="sxs-lookup"><span data-stu-id="ade9d-127">To view network region information</span></span>

  - <span data-ttu-id="ade9d-128">Pour afficher des informations sur toutes vos régions réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="ade9d-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="ade9d-129">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ade9d-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="ade9d-130">Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="ade9d-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="ade9d-131">Créer ou modifier des régions réseau</span><span class="sxs-lookup"><span data-stu-id="ade9d-131">Create or modify network regions</span></span> 

<span data-ttu-id="ade9d-132">Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="ade9d-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ade9d-133">Chaque région réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="ade9d-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ade9d-134">Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute.</span><span class="sxs-lookup"><span data-stu-id="ade9d-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ade9d-135">Vous pouvez utiliser le Panneau de configuration de Skype Entreprise Server pour configurer des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="ade9d-136">Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="ade9d-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ade9d-137">À partir du Panneau de contrôle Skype Entreprise Server, vous pouvez créer, modifier ou supprimer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="ade9d-138">Consultez la rubrique pour créer et modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="ade9d-139">Pour créer une région réseau</span><span class="sxs-lookup"><span data-stu-id="ade9d-139">To create a network region</span></span>

1.  <span data-ttu-id="ade9d-140">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ade9d-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ade9d-141">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ade9d-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ade9d-142">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Région.**</span><span class="sxs-lookup"><span data-stu-id="ade9d-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ade9d-143">Dans la page **Région**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="ade9d-144">Tapez une valeur dans le champ **Nom** de la page **Nouvelle région**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="ade9d-145">Cette valeur doit être unique dans votre déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ade9d-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="ade9d-146">Dans la liste déroulante **Site central**, sélectionnez le site central pour cette région réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="ade9d-p106">La case à cocher **Activer un autre chemin d’accès à l’audio** est activée par défaut. Ce champ détermine si les appels audio seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ade9d-p106">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="ade9d-p107">La case à cocher **Activer un autre chemin d’accès à la vidéo** est activée par défaut. Ce champ détermine si les appels vidéo seront acheminés via un autre chemin si la bande passante adéquate n’existe pas dans le chemin principal. Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement vers Internet. Si vous prévoyez de passer des appels Internet, cette case à cocher doit être activée, indépendamment des paramètres de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ade9d-p107">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="ade9d-155">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région, car son nom seul ne suffit pas à la décrire.</span><span class="sxs-lookup"><span data-stu-id="ade9d-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="ade9d-156">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-156">Click **Commit**.</span></span>

<span data-ttu-id="ade9d-157">Le tableau **Sites associés** n’est pas utilisé pour la création d’une région réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="ade9d-158">Vous associez un site à une région lorsque vous créez ou modifiez le site.</span><span class="sxs-lookup"><span data-stu-id="ade9d-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="ade9d-159">Pour plus d’informations, voir [Gestion du contrôle d’admission des appels pour les sites.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="ade9d-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="ade9d-160">Pour modifier une région réseau</span><span class="sxs-lookup"><span data-stu-id="ade9d-160">To modify a network region</span></span>

1.  <span data-ttu-id="ade9d-161">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ade9d-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ade9d-162">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ade9d-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ade9d-163">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Région.**</span><span class="sxs-lookup"><span data-stu-id="ade9d-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ade9d-164">Dans la page **Région**, cliquez sur la région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="ade9d-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="ade9d-165">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ade9d-166">Dans la page **Modifier la région**, vous pouvez modifier les paramètres permettant d’activer et de désactiver les chemins audio et vidéo alternatifs et modifier également la description (pour plus d’informations, voir la section « Pour créer une région réseau » plus haut dans cette rubrique).</span><span class="sxs-lookup"><span data-stu-id="ade9d-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="ade9d-167">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-167">Click **Commit**.</span></span>

<span data-ttu-id="ade9d-p109">Vous ne pouvez pas modifier les **sites associés** sur cette page. La liste des sites associés est fournie à titre de référence pour vous informer des sites qui seront affectés par la modification des paramètres de région.</span><span class="sxs-lookup"><span data-stu-id="ade9d-p109">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="ade9d-170">Supprimer des régions réseau existantes</span><span class="sxs-lookup"><span data-stu-id="ade9d-170">Delete existing network regions</span></span> 

<span data-ttu-id="ade9d-171">Une région réseau interconnecte diverses parties d’un réseau sur plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="ade9d-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ade9d-172">Chaque région réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="ade9d-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ade9d-173">Le site central est celui du centre de données dans lequel le service de stratégie de bande passante du contrôle d’admission des appels (CAC) s’exécute.</span><span class="sxs-lookup"><span data-stu-id="ade9d-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ade9d-174">Vous pouvez utiliser le Panneau de configuration de Skype Entreprise Server pour configurer des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="ade9d-175">Celles-ci incluent des paramètres qui déterminent si d’autres chemins peuvent être empruntés sur Internet pour les connexions audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="ade9d-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ade9d-176">À partir du Panneau de contrôle Skype Entreprise Server, vous pouvez créer, modifier ou supprimer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="ade9d-177">Consultez la rubrique pour supprimer des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="ade9d-178">Pour supprimer une région réseau</span><span class="sxs-lookup"><span data-stu-id="ade9d-178">To delete a network region</span></span>

1.  <span data-ttu-id="ade9d-179">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ade9d-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ade9d-180">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ade9d-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ade9d-181">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Région.**</span><span class="sxs-lookup"><span data-stu-id="ade9d-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ade9d-182">Dans la page **Région**, cliquez sur la région à supprimer.</span><span class="sxs-lookup"><span data-stu-id="ade9d-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="ade9d-p111">Vous pouvez supprimer plusieurs régions à la fois. Pour cela, appuyez sur la touche Ctrl et, tout en la maintenant enfoncée, sélectionnez plusieurs régions. Pour sélectionner toutes les régions, cliquez sur **Sélectionner tout** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-p111">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ade9d-186">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ade9d-187">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="ade9d-188">Vous ne pouvez pas supprimer une région réseau si elle est associée à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="ade9d-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="ade9d-189">Si vous tentez de supprimer une région associée à un site, vous recevrez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="ade9d-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="ade9d-190">Pour savoir si une région est associée à des sites, sélectionnez-la, puis cliquez sur **Afficher les détails** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="ade9d-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="ade9d-191">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ade9d-191">See Also</span></span>

[<span data-ttu-id="ade9d-192">Gestion des itinéraires de région réseau</span><span class="sxs-lookup"><span data-stu-id="ade9d-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="ade9d-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ade9d-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="ade9d-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ade9d-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="ade9d-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ade9d-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="ade9d-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ade9d-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
