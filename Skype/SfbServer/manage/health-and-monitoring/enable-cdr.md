---
title: Activer l’enregistrement des détails des appels dans Skype Entreprise Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Résumé : Découvrez comment activer les enregistrements des détails des appels dans Skype Entreprise Server.'
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816884"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="f3aed-103">Activer l’enregistrement des détails des appels dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f3aed-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="f3aed-104">**Résumé :** Découvrez comment activer les enregistrements des détails des appels dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f3aed-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="f3aed-p101">La fonctionnalité d’enregistrement des détails des appels recense des informations d’utilisation et de diagnostic sur les activités d’égal à égal, telles que la messagerie instantanée, les appels VoIP (Voice over Internet Protocol), le partage d’application, le transfert de fichiers et les réunions. Vous pouvez utiliser les données d’utilisation pour calculer le retour sur investissement (ROI) et les données de diagnostic pour résoudre les problèmes liés aux activités d’égal à égal et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="f3aed-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="f3aed-107">Procédez comme suit pour activer l’enregistrement des détails des appels dans toute l’organisation ou dans chacun de ses sites.</span><span class="sxs-lookup"><span data-stu-id="f3aed-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="f3aed-108">Pour activer l’enregistrement des détails des appels, vous devez configurer la surveillance et une base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="f3aed-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="f3aed-109">Pour plus d’informations, voir [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="f3aed-109">For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="f3aed-110">Pour activer l’cdr avec le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f3aed-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f3aed-111">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f3aed-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="f3aed-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f3aed-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f3aed-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="f3aed-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="f3aed-114">Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans la table, sur **Action**, puis sur **Activer l’enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="f3aed-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3aed-115">Cette fonctionnalité est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="f3aed-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f3aed-116">Activation de l’cdr à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="f3aed-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f3aed-117">Vous pouvez activer l’Windows PowerShell à l’aide de **l’Windows PowerShell l';Set-CsCdrConfiguration.)**</span><span class="sxs-lookup"><span data-stu-id="f3aed-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="f3aed-118">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f3aed-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f3aed-119">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : gestion de [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="f3aed-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f3aed-120">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f3aed-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="f3aed-121">Pour activer l’enregistrement des détails des appels pour un seul site</span><span class="sxs-lookup"><span data-stu-id="f3aed-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="f3aed-122">Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur True ($True).</span><span class="sxs-lookup"><span data-stu-id="f3aed-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="f3aed-123">Pour désactiver l’enregistrement des détails des appels pour un seul site</span><span class="sxs-lookup"><span data-stu-id="f3aed-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="f3aed-124">Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur False ($False).</span><span class="sxs-lookup"><span data-stu-id="f3aed-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="f3aed-125">La désactivation de l’cdr ne désinstalle pas la surveillance.</span><span class="sxs-lookup"><span data-stu-id="f3aed-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="f3aed-126">Elle interrompt la collecte et le stockage des données d’cdr.</span><span class="sxs-lookup"><span data-stu-id="f3aed-126">It pauses the collection and storage of CDR data.</span></span>

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="f3aed-127">Pour activer l’enregistrement des détails des appels sur plusieurs sites en une seule commande</span><span class="sxs-lookup"><span data-stu-id="f3aed-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="f3aed-128">Cette commande active l’enregistrement des détails des appels pour tous les paramètres de configuration de l’enregistrement des détails des appels utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f3aed-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="f3aed-129">Pour plus d’informations, voir la rubrique d’aide de [l';set-CsCdrConfiguration.)](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f3aed-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3aed-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f3aed-130">See also</span></span>

[<span data-ttu-id="f3aed-131">Planification de la surveillance</span><span class="sxs-lookup"><span data-stu-id="f3aed-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="f3aed-132">Déploiement du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="f3aed-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
