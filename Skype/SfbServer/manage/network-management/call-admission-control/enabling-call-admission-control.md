---
title: Activation du contrôle d’admission des appels
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
description: " Après avoir configuré le réseau de contrôle d’admission des appels, vous devez activer le contrôle d’admission des appels pour appliquer les limites de bande passante."
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816504"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="61b62-103">Activation du contrôle d’admission des appels dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="61b62-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="61b62-104">Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux vous permettant de placer des restrictions sur les transmissions audio et vidéo en fonction de la bande passante disponible.</span><span class="sxs-lookup"><span data-stu-id="61b62-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="61b62-105">Après avoir configuré le réseau CAC, vous devez l’activer pour qu’il applique les limites de bande passante.</span><span class="sxs-lookup"><span data-stu-id="61b62-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="61b62-106">Pour ce faire, vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="61b62-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="61b62-107">Pour activer le contrôle d’accès au contrôle d’accès à partir du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="61b62-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="61b62-108">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="61b62-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="61b62-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="61b62-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="61b62-110">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="61b62-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="61b62-111">Dans la page **Globale**, cliquez sur la configuration **Globale**.</span><span class="sxs-lookup"><span data-stu-id="61b62-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="61b62-112">Un seul réseau peut être configuré pour un déploiement Skype Entreprise Server, il n’y aura donc jamais plus d’une configuration réseau dans la liste.</span><span class="sxs-lookup"><span data-stu-id="61b62-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="61b62-113">Il n’est pas possible de renommer la configuration Globale.</span><span class="sxs-lookup"><span data-stu-id="61b62-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="61b62-114">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="61b62-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="61b62-115">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="61b62-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="61b62-p103">Lorsque vous cliquez sur **Valider**, un test de la configuration est exécuté. La boîte de dialogue **Modifier la configuration globale** se ferme et vous retournez à la page **Globale**. Vous obtiendrez un message d’avertissement si des erreurs ou des incohérences, qui empêcheront la configuration du réseau de fonctionner correctement, sont détectées (par exemple, si chaque région n’est pas connectée aux autres régions via un itinéraire interrégion).</span><span class="sxs-lookup"><span data-stu-id="61b62-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="61b62-p104">Si vous modifiez la configuration du réseau, vous pouvez exécuter de nouveau la vérification de validation. Pour cela, ouvrez la configuration globale et cliquez sur **Valider**. Vous n’avez pas besoin de désactiver d’abord le CAC : ne désactivez pas la case à cocher et cliquez sur **Valider**. Vous pouvez lancer la vérification à tout moment même si vous ne modifiez pas la configuration.</span><span class="sxs-lookup"><span data-stu-id="61b62-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="61b62-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61b62-122">See Also</span></span>

[<span data-ttu-id="61b62-123">Planifier le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="61b62-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="61b62-124">Déploiement du contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="61b62-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="61b62-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="61b62-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="61b62-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="61b62-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="61b62-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="61b62-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
