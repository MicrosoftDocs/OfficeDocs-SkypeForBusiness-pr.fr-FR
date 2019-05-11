---
title: Réinitialisation de la stratégie globale pour l’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous ne pouvez pas supprimer complètement une stratégie globale. À l’aide de l’option **Supprimer** de la stratégie globale réinitialise uniquement la stratégie globale pour les paramètres par défaut, qui ne comportent pas de prise en charge pour les options d’accès utilisateur externe.
ms.openlocfilehash: c2f938219a35de97088c26f81d9d59e46e799ebb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33923173"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="a420d-104">Réinitialiser la stratégie globale pour l’accès des utilisateurs externes dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="a420d-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="a420d-105">Si vous avez créé ou configuré des stratégies d’accès utilisateur externe que vous ne souhaitez plus utiliser, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a420d-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="a420d-106">Supprimer une stratégie de site ou d’utilisateur que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="a420d-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="a420d-107">Réinitialiser la stratégie globale pour les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="a420d-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="a420d-108">Les paramètres de stratégie globale par défaut refuser tout accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="a420d-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="a420d-109">Impossible de supprimer la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="a420d-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="a420d-110">Vous ne pouvez pas supprimer complètement une stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="a420d-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="a420d-111">À l’aide de l’option **Supprimer** de la stratégie globale réinitialise uniquement la stratégie globale pour les paramètres par défaut, qui ne comportent pas de prise en charge pour les options d’accès utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="a420d-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="a420d-112">Pour réinitialiser la stratégie globale pour les paramètres par défaut</span><span class="sxs-lookup"><span data-stu-id="a420d-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="a420d-113">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a420d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a420d-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="a420d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="a420d-115">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, cliquez sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="a420d-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="a420d-116">Sous l’onglet **Stratégie d’accès externe** , cliquez sur la stratégie globale, cliquez sur **Modifier**, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="a420d-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="a420d-117">Lorsque vous y êtes invité à confirmer la suppression, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a420d-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="a420d-118">Un message s’affiche en haut de la page pour vous informer que la stratégie globale a été réinitialisée.</span><span class="sxs-lookup"><span data-stu-id="a420d-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a420d-119">Redéfinition de la stratégie d’accès externe globale à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a420d-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a420d-120">La stratégie d’accès externe globale peut être réinitialisée à l’aide de Windows PowerShell et l’applet de commande Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="a420d-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="a420d-121">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session Windows PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="a420d-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="a420d-122">Pour réinitialiser la stratégie d’accès externe globale</span><span class="sxs-lookup"><span data-stu-id="a420d-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="a420d-123">Cette commande réinitialise la stratégie d’accès externe globale :</span><span class="sxs-lookup"><span data-stu-id="a420d-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="a420d-124">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="a420d-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


