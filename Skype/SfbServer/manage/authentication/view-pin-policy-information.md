---
title: Afficher les informations de stratégie de code confidentiel dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Résumé : Affichez les informations de stratégie de code confidentiel d’un utilisateur pour Skype entreprise Server.'
ms.openlocfilehash: 57a54e960a0c89408f173567a78449cad21de9ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818696"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="ff6b2-103">Afficher les informations de stratégie de code confidentiel dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ff6b2-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="ff6b2-104">**Résumé :** Afficher les informations de stratégie de code confidentiel d’un utilisateur pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="ff6b2-105">Vous pouvez utiliser l’onglet **stratégie de code confidentiel** pour afficher l’authentification par code confidentiel (pin) des utilisateurs qui se connectent à Skype entreprise avec des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="ff6b2-106">Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="ff6b2-107">Suivez cette procédure pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ff6b2-108">Pour afficher des informations sur une stratégie de code confidentiel dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ff6b2-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ff6b2-109">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="ff6b2-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="ff6b2-110">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ff6b2-111">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="ff6b2-112">Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ff6b2-113">Affichage de stratégies de code confidentiel à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff6b2-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ff6b2-114">Vous pouvez également afficher les stratégies de code confidentiel à l’aide de Windows PowerShell et de l’applet de cmdlet Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="ff6b2-115">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ff6b2-116">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="ff6b2-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ff6b2-117">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ff6b2-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="ff6b2-118">Pour afficher les stratégies de code confidentiel</span><span class="sxs-lookup"><span data-stu-id="ff6b2-118">To view PIN policies</span></span>

<span data-ttu-id="ff6b2-119">Pour afficher des informations sur toutes les stratégies de code confidentiel, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="ff6b2-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="ff6b2-120">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="ff6b2-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="ff6b2-121">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="ff6b2-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff6b2-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff6b2-122">See also</span></span>

[<span data-ttu-id="ff6b2-123">Créer une nouvelle stratégie de code confidentiel dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ff6b2-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
