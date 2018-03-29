---
title: Affichage des informations de stratégie de code confidentiel dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Résumé : Afficher les informations de stratégie de code PIN d’un utilisateur pour Skype pour Business Server 2015.'
ms.openlocfilehash: 3b62dae5cbd29c4622e30c6369a498eb48e126c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="view-pin-policy-information-in-skype-for-business-server-2015"></a><span data-ttu-id="9683c-103">Affichage des informations de stratégie de code confidentiel dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="9683c-103">View PIN policy information in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9683c-104">**Résumé :** Permet d’afficher les informations de stratégie code PIN d’un utilisateur pour Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9683c-104">**Summary:** View a user's PIN policy information for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9683c-105">Vous pouvez utiliser l’onglet **Stratégie de code PIN** à vue identification personnel numéro (code PIN) l’authentification des utilisateurs qui se connectent à Skype pour les entreprises avec des téléphones IP.</span><span class="sxs-lookup"><span data-stu-id="9683c-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="9683c-106">Pour utiliser l’authentification par code confidentiel, assurez-vous que l’option **Activer l’authentification par code confidentiel** est sélectionnée dans les paramètres du service web.</span><span class="sxs-lookup"><span data-stu-id="9683c-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="9683c-107">Suivez cette procédure étapes pour modifier une stratégie de code confidentiel au niveau du site ou de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9683c-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="9683c-108">Pour afficher des informations sur une stratégie de code PIN dans Skype pour le panneau de configuration de Business Server</span><span class="sxs-lookup"><span data-stu-id="9683c-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9683c-109">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou dispose de droits d’utilisateur équivalent), ou le rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur sur le réseau dans lequel vous avez déployé Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9683c-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="9683c-110">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="9683c-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9683c-111">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.</span><span class="sxs-lookup"><span data-stu-id="9683c-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="9683c-112">Dans la page **Stratégie de code confidentiel**, cliquez sur une stratégie, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="9683c-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9683c-113">Affichage des stratégies de code PIN à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9683c-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9683c-114">Vous pouvez également afficher les stratégies de code PIN à l’aide de Windows PowerShell et l’applet de commande Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="9683c-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="9683c-115">Cette applet de commande peut être exécuté à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9683c-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9683c-116">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="9683c-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9683c-117">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9683c-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="9683c-118">Pour afficher les stratégies de code confidentiel</span><span class="sxs-lookup"><span data-stu-id="9683c-118">To view PIN policies</span></span>

<span data-ttu-id="9683c-119">Pour afficher des informations sur toutes les stratégies de votre code PIN, tapez la commande suivante dans la Skype pour Business Server Management Shell et puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="9683c-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsPinPolicy
  ```

<span data-ttu-id="9683c-120">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="9683c-120">That will return information similar to this:</span></span>

  ```
  Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
  ```

<span data-ttu-id="9683c-121">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9683c-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9683c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9683c-122">See also</span></span>

#### 

[<span data-ttu-id="9683c-123">Créer une nouvelle stratégie de code PIN dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9683c-123">Create a new PIN policy in Skype for Business Server 2015</span></span>](create-a-new-pin-policy.md)

