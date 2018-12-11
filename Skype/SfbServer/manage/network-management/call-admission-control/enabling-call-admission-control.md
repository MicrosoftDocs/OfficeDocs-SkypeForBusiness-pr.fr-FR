---
title: Activation du contrôle d’admission des appels
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Après avoir configuré l’appel d’admission des appels (CAC) réseau, vous devez activer CAC appliquer les limitations de bande passante."
ms.openlocfilehash: 9c264305a38bf4bf9ef3716c5df82d74155e8936
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222834"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="a92f6-103">Activer le contrôle d’admission des appels d’appel dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="a92f6-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="a92f6-104">Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux qui permettant de définir des restrictions pour les transmissions audio et vidéo en fonction de la bande passante disponible.</span><span class="sxs-lookup"><span data-stu-id="a92f6-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="a92f6-105">Après avoir configuré le réseau CAC, vous devez activer CAC appliquer les limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="a92f6-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="a92f6-106">Vous pouvez utiliser la Skype pour Business Server Control Panel pour effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="a92f6-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="a92f6-107">Pour activer CAC à partir de la Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="a92f6-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a92f6-108">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a92f6-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a92f6-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a92f6-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="a92f6-110">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="a92f6-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="a92f6-111">Dans la page **globale** , cliquez sur la configuration **globale** .</span><span class="sxs-lookup"><span data-stu-id="a92f6-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="a92f6-112">Seul réseau peut être configuré pour n’importe quel Skype pour le déploiement de serveur d’entreprise, il y aura jamais plus d’une configuration réseau dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a92f6-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="a92f6-113">Vous ne pouvez pas renommer la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="a92f6-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="a92f6-114">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a92f6-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="a92f6-115">Dans la page **Modifier la configuration globale** , activez la case à cocher **Activer le contrôle d’admission des appels** , puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a92f6-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="a92f6-116">Lorsque vous cliquez sur **Valider**, vous exécutez un test de la configuration.</span><span class="sxs-lookup"><span data-stu-id="a92f6-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="a92f6-117">Ferme la boîte de dialogue **Modifier les paramètres globaux** , vous revenez à la page **Global** .</span><span class="sxs-lookup"><span data-stu-id="a92f6-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="a92f6-118">Vous recevrez un avertissement si des erreurs ou des incohérences sont découvertes dans la configuration de votre réseau qui l’empêche de fonctionner correctement (par exemple, si chaque région n’est pas connectée à toutes les autres régions via un itinéraire inter-région).</span><span class="sxs-lookup"><span data-stu-id="a92f6-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="a92f6-119">Si vous apportez des modifications à la configuration de votre réseau, vous pouvez exécuter à nouveau le contrôle de validation en ouvrant la configuration globale et en cliquant sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a92f6-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="a92f6-120">Vous n’avez pas besoin de désactiver CAC tout d’abord : laissez la case à cocher activée et cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a92f6-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="a92f6-121">Vous pouvez le faire à tout moment sans apporter de modifications de configuration.</span><span class="sxs-lookup"><span data-stu-id="a92f6-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="a92f6-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a92f6-122">See Also</span></span>

[<span data-ttu-id="a92f6-123">Planification du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="a92f6-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="a92f6-124">Déploiement du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="a92f6-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="a92f6-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a92f6-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="a92f6-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a92f6-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="a92f6-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a92f6-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
