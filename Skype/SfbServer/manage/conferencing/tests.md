---
title: Test de la Conférence rendez-vous dans Skype entreprise Server
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
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Résumé : Découvrez comment tester les conférences rendez-vous dans Skype entreprise Server.'
ms.openlocfilehash: 838e04d7cb6d17e98df2b6fa0dbe3f3d46a5ecad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818465"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="1973d-103">Test de la Conférence rendez-vous dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1973d-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="1973d-104">**Résumé :** Découvrez comment tester les conférences rendez-vous dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1973d-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="1973d-105">Pour terminer la vérification de votre configuration de conférence rendez-vous, vous pouvez chercher des plans de numérotation dont la région de conférence rendez-vous n’est utilisée par aucun numéro d’accès et des numéros d’accès que vous n’avez pas spécifiés dans une région de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1973d-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="1973d-106">Vous devez également vérifier que la page web Paramètres de conférence rendez-vous et les numéros d’accès entrants fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="1973d-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="1973d-107">Trouver des plans de numérotation dont la région de conférence rendez-vous n’est utilisée par aucun numéro d’accès</span><span class="sxs-lookup"><span data-stu-id="1973d-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="1973d-108">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1973d-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="1973d-109">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1973d-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1973d-110">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="1973d-110">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="1973d-111">Cette applet de commande renvoie tous les plans de numérotation dont la région de conférence rendez-vous n’est pas utilisée par un numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="1973d-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="1973d-112">Pour plus d’informations, consultez la rubrique [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1973d-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="1973d-113">REcherche de numéros d’accès sans région affectée</span><span class="sxs-lookup"><span data-stu-id="1973d-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="1973d-114">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1973d-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="1973d-115">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1973d-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1973d-116">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="1973d-116">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="1973d-117">Cette applet de commande renvoie tous les numéros d’accès de conférences rendez-vous qui ne sont pas associés à une région.</span><span class="sxs-lookup"><span data-stu-id="1973d-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="1973d-118">Pour plus d’informations, consultez la rubrique [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1973d-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="1973d-119">Test de la page web et des numéros d’accès</span><span class="sxs-lookup"><span data-stu-id="1973d-119">Test webpage and access numbers</span></span>

<span data-ttu-id="1973d-120">Pour vérifier que la page web Paramètres de conférence rendez-vous et les numéros d’accès entrants fonctionnent correctement, vous devez :</span><span class="sxs-lookup"><span data-stu-id="1973d-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="1973d-121">tester la page web Paramètres de conférence rendez-vous en vous connectant à l’URL simple ;</span><span class="sxs-lookup"><span data-stu-id="1973d-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="1973d-p102">tester les numéros d’accès d’un pool spécifique en exécutant le script présenté dans la suite de cette rubrique. Ce script simule les appels vers les numéros d’accès. Pour l’utiliser, vous devez disposer de l’adresse SIP et des informations d’identification de l’un des clients de communications unifiées hébergés sur le pool.</span><span class="sxs-lookup"><span data-stu-id="1973d-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="1973d-125">Pour tester les numéros d’accès à un pool spécifique</span><span class="sxs-lookup"><span data-stu-id="1973d-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="1973d-126">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1973d-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="1973d-127">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1973d-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1973d-128">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="1973d-128">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="1973d-129">Le rapport obtenu indique Opération réussie ou Échec ainsi que des informations de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="1973d-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="1973d-130">L’indicateur-verbose fournit des informations plus détaillées sur le nombre de numéros d’accès qui ont été trouvés et leur détails.</span><span class="sxs-lookup"><span data-stu-id="1973d-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="1973d-131">Pour plus d’informations, consultez la rubrique [test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1973d-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

