---
title: Installer et configurer Busy options pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: Découvrez comment installer et configurer Busy options dans Skype entreprise Server.
ms.openlocfilehash: bdc713c50fa63ac208c7476916110c14fca8f387
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604211"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="7d26a-103">Installer et configurer Busy options pour Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7d26a-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="7d26a-104">Découvrez comment installer et configurer Busy options dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7d26a-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="7d26a-105">Busy options est une nouvelle stratégie de voix introduite dans la mise à jour cumulative de juillet 2016 qui vous permet de configurer le mode de traitement des appels entrants lorsqu’un utilisateur est déjà dans un appel ou une conférence ou lorsqu’un appel est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="7d26a-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="7d26a-106">Les nouveaux appels ou les appels entrants peuvent être rejetés avec un signal occupé ou transférés vers la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="7d26a-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="7d26a-107">Si Busy options est activée pour l’organisation, tous les utilisateurs de l’entreprise, qu’il s’agisse des utilisateurs de voix entreprise ou non, peuvent utiliser les options de configuration suivantes :</span><span class="sxs-lookup"><span data-stu-id="7d26a-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="7d26a-108">Busy on Busy : les nouveaux appels entrants seront rejetés avec un signal occupé si l’utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="7d26a-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="7d26a-109">Messagerie vocale sur occupé : dans lequel les nouveaux appels entrants seront transférés vers la messagerie vocale si l’utilisateur est occupé.</span><span class="sxs-lookup"><span data-stu-id="7d26a-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="7d26a-110">Quelle que soit la façon dont les options occupées sont configurées, les utilisateurs d’un appel ou d’une conférence, ou ceux ayant mis un appel en attente, ne sont pas autorisés à lancer de nouveaux appels ou de nouvelles conférences.</span><span class="sxs-lookup"><span data-stu-id="7d26a-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="7d26a-111">Pour plus d’informations sur la fonctionnalité Busy options, reportez-vous à la rubrique [plan for Busy options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="7d26a-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="7d26a-112">Installer</span><span class="sxs-lookup"><span data-stu-id="7d26a-112">Install</span></span>

<span data-ttu-id="7d26a-113">Assurez-vous que la dernière version de Skype entreprise Server est installée et que vous avez installé le correctif le plus récent.</span><span class="sxs-lookup"><span data-stu-id="7d26a-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="7d26a-114">Pour ce faire, arrêtez tous les services, puis exécutez le programme d’installation de la mise à jour de Skype entreprise Server comme suit :</span><span class="sxs-lookup"><span data-stu-id="7d26a-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="7d26a-115">Exécutez la commande Stop-CsWindowsService.</span><span class="sxs-lookup"><span data-stu-id="7d26a-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="7d26a-116">Exécutez le programme d’installation d’installation skypeserverupdateinstaller. exe sur chaque serveur frontal d’un pool.</span><span class="sxs-lookup"><span data-stu-id="7d26a-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="7d26a-117">Exécutez le programme d’installation de installation skypeserverupdateinstaller. exe sur chaque serveur Survivable Branch Server (SBS), si vous voulez garantir la prise en charge du basculement sur SBS.</span><span class="sxs-lookup"><span data-stu-id="7d26a-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="7d26a-118">Le programme d’installation déploiera la dernière version de l’application options Busy.</span><span class="sxs-lookup"><span data-stu-id="7d26a-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="7d26a-119">Toutefois, l’application n’est pas activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="7d26a-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="7d26a-120">Pour activer l’application, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7d26a-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="7d26a-121">Exécutez l’applet de commande [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) pour activer les options Busy de manière globale, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="7d26a-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="7d26a-122">Ensuite, si le site possède une stratégie de voix, vous devez activer la fonctionnalité Busy options pour la stratégie de voix comme suit :</span><span class="sxs-lookup"><span data-stu-id="7d26a-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="7d26a-123">Tout d’abord, exécutez [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) pour récupérer le nom du site :</span><span class="sxs-lookup"><span data-stu-id="7d26a-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="7d26a-124">Utilisez la valeur IDENTITY (par exemple : site : Redmond1) extrait de Get-CsSite pour récupérer la stratégie de voix du site comme suit :</span><span class="sxs-lookup"><span data-stu-id="7d26a-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="7d26a-125">S’il existe une stratégie de voix pour le site, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7d26a-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="7d26a-126">Ensuite, exécutez la cmdlet [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) pour ajouter des options Busy à la liste des applications serveur, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="7d26a-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="7d26a-127">Vous devez remplacer% FQDN% par le nom de domaine complet d’un pool spécifique.</span><span class="sxs-lookup"><span data-stu-id="7d26a-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="7d26a-128">Ensuite, exécutez la cmdlet [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) pour mettre à jour les rôles RBAC (contrôle d’accès basé sur un rôle) pour les applets de commande Busy options comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="7d26a-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="7d26a-129">Enfin, démarrez les services Windows Skype entreprise Server sur tous les serveurs frontaux de tous les pools où Busy options a été installé et activé en exécutant la commande [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="7d26a-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="7d26a-130">Configurer</span><span class="sxs-lookup"><span data-stu-id="7d26a-130">Configure</span></span>

<span data-ttu-id="7d26a-131">Pour configurer Busy options, utilisez la cmdlet [Set-applet csbusyoptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7d26a-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="7d26a-132">Par exemple, la commande suivante configure la fonctionnalité Busy options pour l’utilisateur « Ken Myer ».</span><span class="sxs-lookup"><span data-stu-id="7d26a-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="7d26a-133">Dans cette configuration, tout appel à « Ken Myer » renverra un signal occupé lorsqu’il est déjà en communication :</span><span class="sxs-lookup"><span data-stu-id="7d26a-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="7d26a-134">Dans l’exemple suivant, la commande configure la fonctionnalité Busy options pour l’utilisateur « Chrystal Velasquez ».</span><span class="sxs-lookup"><span data-stu-id="7d26a-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="7d26a-135">Dans cette configuration, les nouveaux appels entrants vers « Chrystal Velasquez » seront transférés vers la messagerie vocale lorsqu’elle sera déjà en communication :</span><span class="sxs-lookup"><span data-stu-id="7d26a-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="7d26a-136">Vous pouvez récupérer des informations de configuration sur les options occupées à l’aide de la cmdlet [Get-applet csbusyoptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7d26a-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="7d26a-137">L’exemple suivant renvoie le paramètre Busy options pour « KenMyer@Contoso.com » :</span><span class="sxs-lookup"><span data-stu-id="7d26a-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="7d26a-138">Vous pouvez supprimer les options Busy à l’aide de l’applet de commande [Remove-applet csbusyoptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7d26a-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="7d26a-139">La commande suivante supprime les options Busy pour « Ken Myer » :</span><span class="sxs-lookup"><span data-stu-id="7d26a-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="7d26a-140">Pour obtenir des informations détaillées sur les applets de commande que vous utilisez pour configurer Busy options, consultez le contenu de référence technique pour [Set-applet csbusyoptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-applet csbusyoptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)et [Remove-applet csbusyoptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span><span class="sxs-lookup"><span data-stu-id="7d26a-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="7d26a-141">Activer la journalisation</span><span class="sxs-lookup"><span data-stu-id="7d26a-141">Enable logging</span></span>

<span data-ttu-id="7d26a-142">Pour activer la journalisation des options occupées à l’aide du service de journalisation centralisée, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="7d26a-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="7d26a-143">Vérifier et résoudre les problèmes</span><span class="sxs-lookup"><span data-stu-id="7d26a-143">Verify and troubleshoot</span></span>

<span data-ttu-id="7d26a-144">Après avoir installé Busy options, vous pouvez vérifier que l’installation a réussi à l’aide de la cmdlet [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) pour récupérer la liste des applications serveur.</span><span class="sxs-lookup"><span data-stu-id="7d26a-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="7d26a-145">Si Busy options est correctement installée, la sortie de l’applet de commande doit afficher la configuration Busy options comme suit :</span><span class="sxs-lookup"><span data-stu-id="7d26a-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="7d26a-146">Vous pouvez également utiliser l’observateur d’événements Windows pour vérifier que l’installation des options occupées a réussi et que Skype entreprise Server a correctement chargé les options occupées.</span><span class="sxs-lookup"><span data-stu-id="7d26a-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="7d26a-147">Pour vérifier Busy options, ouvrez l' **Observateur d'\> événements-journaux des applications\> et des services-serveur Skype (ou Lync) Server** et recherchez l’ID d’événement = 30253.</span><span class="sxs-lookup"><span data-stu-id="7d26a-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
