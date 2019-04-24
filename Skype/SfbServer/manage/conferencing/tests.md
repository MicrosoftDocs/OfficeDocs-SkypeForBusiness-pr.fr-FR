---
title: Conférence rendez-vous test dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Résumé : Découvrez comment tester la conférence rendez-vous dans Skype pour Business Server.'
ms.openlocfilehash: 99d91a4d3e9729da7b86f723f4a980a887d88b5f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197771"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="01c79-103">Conférence rendez-vous test dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="01c79-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="01c79-104">**Résumé :** Découvrez comment tester la conférence rendez-vous dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="01c79-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="01c79-105">Pour terminer la vérification de votre configuration de conférence rendez-vous, vous pouvez chercher des plans de numérotation dont la région de conférence rendez-vous n’est utilisée par aucun numéro d’accès et des numéros d’accès que vous n’avez pas spécifiés dans une région de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="01c79-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="01c79-106">Vous devez également vérifier que la page web Paramètres de conférence rendez-vous et les numéros d’accès entrants fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="01c79-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="01c79-107">Trouver des plans de numérotation dont la région de conférence rendez-vous n’est utilisée par aucun numéro d’accès</span><span class="sxs-lookup"><span data-stu-id="01c79-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="01c79-108">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="01c79-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="01c79-109">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="01c79-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="01c79-110">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="01c79-110">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="01c79-111">Cette applet de commande renvoie tous les plans de numérotation dont la région de conférence rendez-vous n’est pas utilisée par un numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="01c79-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="01c79-112">Pour plus d’informations, voir [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="01c79-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="01c79-113">REcherche de numéros d’accès sans région affectée</span><span class="sxs-lookup"><span data-stu-id="01c79-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="01c79-114">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="01c79-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="01c79-115">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="01c79-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="01c79-116">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="01c79-116">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="01c79-117">Cette applet de commande renvoie tous les numéros d’accès de conférences rendez-vous qui ne sont pas associés à une région.</span><span class="sxs-lookup"><span data-stu-id="01c79-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="01c79-118">Pour plus d’informations, voir [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="01c79-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="01c79-119">Test de la page web et des numéros d’accès</span><span class="sxs-lookup"><span data-stu-id="01c79-119">Test webpage and access numbers</span></span>

<span data-ttu-id="01c79-120">Pour vérifier que la page web Paramètres de conférence rendez-vous et les numéros d’accès entrants fonctionnent correctement, vous devez :</span><span class="sxs-lookup"><span data-stu-id="01c79-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="01c79-121">tester la page web Paramètres de conférence rendez-vous en vous connectant à l’URL simple ;</span><span class="sxs-lookup"><span data-stu-id="01c79-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="01c79-p102">tester les numéros d’accès d’un pool spécifique en exécutant le script présenté dans la suite de cette rubrique. Ce script simule les appels vers les numéros d’accès. Pour l’utiliser, vous devez disposer de l’adresse SIP et des informations d’identification de l’un des clients de communications unifiées hébergés sur le pool.</span><span class="sxs-lookup"><span data-stu-id="01c79-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="01c79-125">Pour tester les numéros d’accès à un pool spécifique</span><span class="sxs-lookup"><span data-stu-id="01c79-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="01c79-126">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="01c79-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="01c79-127">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="01c79-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="01c79-128">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="01c79-128">Run the following at the command prompt:</span></span>
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="01c79-129">Le rapport obtenu indique Opération réussie ou Échec ainsi que des informations de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="01c79-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="01c79-130">-Verbose indicateur fournit plus d’informations sur l’accès combien numéros ont été détectés et plus d’informations sur les.</span><span class="sxs-lookup"><span data-stu-id="01c79-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="01c79-131">Pour plus d’informations, voir [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="01c79-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

