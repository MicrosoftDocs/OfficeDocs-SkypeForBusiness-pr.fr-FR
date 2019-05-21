---
title: Activation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Après avoir configuré le réseau CAC (Call Admission Control), vous devez activer le CAC pour appliquer les limitations de bande passante."
ms.openlocfilehash: cbe3ad690f7061611a91474ce6df1fe39d84b0fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279549"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="1b717-103">Activation du contrôle d’admission des appels dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b717-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="1b717-104">Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux qui permettant de définir des restrictions pour les transmissions audio et vidéo en fonction de la bande passante disponible.</span><span class="sxs-lookup"><span data-stu-id="1b717-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="1b717-105">Après avoir configuré le réseau CAC, vous devez activer le CAC pour appliquer les limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="1b717-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="1b717-106">Pour cela, vous pouvez utiliser le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b717-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="1b717-107">Pour activer le CAC dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b717-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1b717-108">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1b717-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1b717-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b717-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1b717-110">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="1b717-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="1b717-111">Dans la page **Global** , cliquez sur configuration **globale** .</span><span class="sxs-lookup"><span data-stu-id="1b717-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="1b717-112">Un seul réseau peut être configuré pour n’importe quel déploiement de Skype entreprise Server, de sorte qu’il ne reste jamais plus d’une configuration réseau dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1b717-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="1b717-113">Vous ne pouvez pas renommer la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="1b717-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="1b717-114">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1b717-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1b717-115">Dans la page **modifier le paramètre global** , activez la case à cocher **activer le contrôle d’admission des appels** , puis cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="1b717-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="1b717-116">Lorsque vous cliquez sur **valider**, vous effectuez un test de la configuration.</span><span class="sxs-lookup"><span data-stu-id="1b717-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="1b717-117">La boîte de dialogue **modifier les paramètres globaux** se ferme et vous permet de revenir à la page **globale** .</span><span class="sxs-lookup"><span data-stu-id="1b717-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="1b717-118">Vous recevez un avertissement en cas d’erreurs ou d’éventuelles incohérences détectées dans votre configuration réseau qui empêche celle-ci de fonctionner correctement (par exemple, si chaque région n’est pas connectée à une autre région par le biais d’un itinéraire interrégion).</span><span class="sxs-lookup"><span data-stu-id="1b717-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="1b717-119">Si vous apportez des modifications à la configuration de votre réseau, vous pouvez exécuter de nouveau le contrôle de validation en ouvrant la configuration globale et en cliquant sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="1b717-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="1b717-120">Vous n’avez pas besoin de désactiver le CAC d’abord: laissez la case à cocher activée, puis cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="1b717-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="1b717-121">Vous pouvez le faire à tout moment sans apporter de modifications à la configuration.</span><span class="sxs-lookup"><span data-stu-id="1b717-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b717-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b717-122">See Also</span></span>

[<span data-ttu-id="1b717-123">Planification du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="1b717-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="1b717-124">Déploiement du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="1b717-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="1b717-125">Get-Csnetworkconfiguration permettent</span><span class="sxs-lookup"><span data-stu-id="1b717-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="1b717-126">Set-Csnetworkconfiguration permettent</span><span class="sxs-lookup"><span data-stu-id="1b717-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="1b717-127">Remove-Csnetworkconfiguration permettent</span><span class="sxs-lookup"><span data-stu-id="1b717-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
