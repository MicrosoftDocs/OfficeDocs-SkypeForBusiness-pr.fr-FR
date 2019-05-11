---
title: Installer et configurer les options Occupé pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Découvrez comment installer et configurer les Options de disponibilité dans Skype pour Business Server.
ms.openlocfilehash: 5e68dd61ce668a80ccbdeb3faae5875825992650
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892362"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="c8bb3-103">Installer et configurer les options Occupé pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="c8bb3-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="c8bb3-104">Découvrez comment installer et configurer les Options de disponibilité dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="c8bb3-105">Busy Options est une nouvelle stratégie de voix de la mise à jour cumulative de juillet 2016, qui vous permet de configurer la manière dont les appels entrants sont gérés lorsqu'un utilisateur participe déjà à un appel ou à une conférence, ou lorsqu'il a mis un appel en attente.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="c8bb3-106">Les nouveaux appels ou les appels entrants peuvent être rejetés avec une tonalité d’occupation ou sont transférés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="c8bb3-107">Si Busy Options est activée pour l'organisation, l'ensemble des utilisateurs de l'entreprise, qu'il s'agisse des utilisateurs de Voix Entreprise ou non, peuvent utiliser les options de configuration suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="c8bb3-108">Busy on Busy : les nouveaux appels entrants seront rejetés avec une tonalité d’occupation si l'utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="c8bb3-109">Voicemail on Busy : les nouveaux appels entrants seront transférés vers la messagerie si l'utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="c8bb3-110">Quelle que soit la manière dont ils ont configuré Busy Option, les utilisateurs participant à un appel ou une conférence, ou ceux ayant mis un appel en absence, peuvent toujours lancer de nouveaux appels ou de nouvelles conférences.  </span><span class="sxs-lookup"><span data-stu-id="c8bb3-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="c8bb3-111">Pour plus d'informations sur la fonctionnalité Busy Options, reportez-vous à la rubrique [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="c8bb3-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="c8bb3-112">Installation </span><span class="sxs-lookup"><span data-stu-id="c8bb3-112">Install</span></span>

<span data-ttu-id="c8bb3-113">Assurez-vous que vous avez la dernière version de Skype pour Business Server est installé et que vous avez installé le correctif le plus récent.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="c8bb3-114">Pour ce faire, tout d’abord arrêter tous les services, puis exécutez la Skype pour le programme d’installation de la mise à jour Business Server comme suit :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="c8bb3-115">Exécutez la commande Stop-CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="c8bb3-116">Exécutez le programme d'installation SkypeServerUpdateInstaller.exe sur chaque serveur frontal d’un pool.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="c8bb3-117">Exécutez le programme d'installation SkypeServerUpdateInstaller.exe sur chaque serveur Survivable Branch Server si vous souhaitez prendre en charge le basculement sur SBS.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="c8bb3-p103">Le programme d’installation déploiera la version la plus récente de l’application Busy Options mais l’application n’est pas activée par défaut. Pour l'activer, procédez de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-p103">The installer will deploy the latest version of the Busy Options application. However, the application is not enabled by default. To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="c8bb3-121">Exécutez l’applet de commande [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) pour activer globalement Options occupé (e) comme indiqué dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="c8bb3-122">Si une stratégie de voix est en place sur le site, activez ensuite Busy Options pour la stratégie de voix de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="c8bb3-123">Tout d’abord, exécutez [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) pour récupérer le nom du site :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```
   Get-CsSite
   ```

    <span data-ttu-id="c8bb3-124">Utilisez la valeur d’identité (par exemple : Site : Redmond1) extraites de Get-CsSite pour récupérer la stratégie de voix du site comme suit :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="c8bb3-125">Si une stratégie de voix existe pour le site, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-125">If a voice policy exists for the site, run the following command:</span></span>

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="c8bb3-126">Ensuite, exécutez l’applet de commande [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) pour ajouter des Options occupé (e) à la liste des applications de serveur comme indiqué dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="c8bb3-127">Vous devez remplacer le nom de domaine complet % avec le nom de domaine complet d’un pool spécifique.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="c8bb3-128">Ensuite, exécutez l’applet de commande [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) pour mettre à jour les rôles accès basé sur un rôle RBAC (contrôle) pour les applets de commande Options occupé (e), comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```
   Update-CsAdminRole
   ```

5. <span data-ttu-id="c8bb3-129">Enfin, démarrer le Skype pour les services Business serveur Windows sur tous les serveurs frontaux dans tous les pools où Options occupé (e) a été installée et activée en exécutant la commande [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="c8bb3-130">Configuration</span><span class="sxs-lookup"><span data-stu-id="c8bb3-130">Configure</span></span>

<span data-ttu-id="c8bb3-131">Pour configurer la fonctionnalité Busy Options, utilisez l'applet de commande [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx).  </span><span class="sxs-lookup"><span data-stu-id="c8bb3-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="c8bb3-p104">Par exemple, la commande suivante configure la fonctionnalité Busy Options pour l'utilisateur « Ken Myer ». Dans cette configuration, les appels vers « Ken Myer » seront retournés avec une tonalité d’occupation lorsqu'il sera déjà en communication :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-p104">For example, the following command configures busy options for the user "Ken Myer". In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="c8bb3-134">Dans l'exemple suivant, la commande configure la fonctionnalité Busy Options pour l'utilisateur « Chrystal Velasquez ».</span><span class="sxs-lookup"><span data-stu-id="c8bb3-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="c8bb3-135">Dans cette configuration, les nouveaux appels entrants vers « Chrystal Velasquez » seront transférés vers la messagerie vocale lorsqu'elle sera déjà en communication :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="c8bb3-136">Vous pouvez récupérer les informations relatives à la configuration de Busy Options à l'aide de l'applet de commande [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx).</span><span class="sxs-lookup"><span data-stu-id="c8bb3-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="c8bb3-137">L’exemple suivant renvoie le paramètre Options de disponibilité pour « KenMyer@Contoso.com » :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="c8bb3-138">Vous pouvez supprimer Busy Options à l'aide de l'applet de commande [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="c8bb3-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="c8bb3-139">La commande suivante supprime la fonctionnalité Busy Options pour « Ken Myer » :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-139">The following command removes Busy Options for "Ken Myer":</span></span>

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="c8bb3-140">Pour obtenir des informations détaillées sur les applets de commande vous permet de configurer les Options de disponibilité, consultez la référence technique pour [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)et [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="c8bb3-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="c8bb3-141">Activation de la journalisation</span><span class="sxs-lookup"><span data-stu-id="c8bb3-141">Enable logging</span></span>

<span data-ttu-id="c8bb3-142">Pour activer la journalisation pour la fonctionnalité Busy Options à l'aide de Centralized Logging Service, indiquez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="c8bb3-143">Vérification et dépannage</span><span class="sxs-lookup"><span data-stu-id="c8bb3-143">Verify and troubleshoot</span></span>

<span data-ttu-id="c8bb3-144">Après avoir installé les Options de disponibilité, vous pouvez vérifier que l’installation a réussi à l’aide de l’applet de commande [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) pour récupérer la liste des applications de serveur.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="c8bb3-145">Si Busy Options est correctement installée, le résultat de l'applet de commande devrait afficher la configuration de Busy Options comme suit :</span><span class="sxs-lookup"><span data-stu-id="c8bb3-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="c8bb3-146">Vous pouvez également utiliser l’Observateur d’événements Windows pour vérifier la réussite de l’installation Options occupé (e) et que Skype pour Business Server chargée correctement Options occupé (e).</span><span class="sxs-lookup"><span data-stu-id="c8bb3-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="c8bb3-147">Pour vérifier les Options de disponibilité, ouvrez **Observateur d’événements -\> journaux des applications et Services -\> Skype (ou Lync) Server** , puis recherchez l’ID d’événement = 30253.</span><span class="sxs-lookup"><span data-stu-id="c8bb3-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
