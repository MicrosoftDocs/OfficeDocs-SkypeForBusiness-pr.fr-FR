---
title: Activer l’enregistrement des détails des appels dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Résumé : Découvrez comment activer les enregistrements d’enregistrements des détails des appels dans Skype entreprise Server.'
ms.openlocfilehash: 015ac3b57420401894e82c267e9737990ca7affb
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767056"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a><span data-ttu-id="d01fd-103">Activer l’enregistrement des détails des appels dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d01fd-103">Enable call detail recording in Skype for Business Server</span></span>

<span data-ttu-id="d01fd-104">**Résumé :** Découvrez comment activer les enregistrements d’enregistrements des détails des appels dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d01fd-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server.</span></span>

<span data-ttu-id="d01fd-p101">La fonctionnalité d’enregistrement des détails des appels recense des informations d’utilisation et de diagnostic sur les activités d’égal à égal, telles que la messagerie instantanée, les appels VoIP (Voice over Internet Protocol), le partage d’application, le transfert de fichiers et les réunions. Vous pouvez utiliser les données d’utilisation pour calculer le retour sur investissement (ROI) et les données de diagnostic pour résoudre les problèmes liés aux activités d’égal à égal et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="d01fd-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="d01fd-107">Procédez comme suit pour activer l’enregistrement des détails des appels dans toute l’organisation ou dans chacun de ses sites.</span><span class="sxs-lookup"><span data-stu-id="d01fd-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="d01fd-p102">Pour activer l’enregistrement des détails des appels, vous devez configurer la surveillance et une base de données de surveillance. Pour plus d’informations, voir [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="d01fd-p102">In order to enable CDR you must configure monitoring and a monitoring database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="d01fd-110">Pour activer le CDR avec Skype entreprise Server panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="d01fd-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="d01fd-111">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="d01fd-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="d01fd-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d01fd-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d01fd-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="d01fd-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4. <span data-ttu-id="d01fd-114">Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans la table, sur **Action**, puis sur **Activer l’enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="d01fd-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d01fd-115">Cette fonctionnalité est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="d01fd-115">CDR is enabled by default.</span></span>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d01fd-116">Activation de CDR à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d01fd-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d01fd-117">Vous pouvez activer le CDR à l’aide de Windows PowerShell et de l’applet **de passe Set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d01fd-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d01fd-118">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d01fd-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d01fd-119">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="d01fd-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d01fd-120">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d01fd-120">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="d01fd-121">Pour activer l’enregistrement des détails des appels pour un seul site</span><span class="sxs-lookup"><span data-stu-id="d01fd-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="d01fd-122">Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur True ($True).</span><span class="sxs-lookup"><span data-stu-id="d01fd-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="d01fd-123">Pour désactiver l’enregistrement des détails des appels pour un seul site</span><span class="sxs-lookup"><span data-stu-id="d01fd-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="d01fd-p104">Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur False ($False). Cette désactivation n’a pas pour effet de désinstaller la surveillance ; il interrompt la collecte et le stockage des données d’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="d01fd-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>

  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="d01fd-127">Pour activer l’enregistrement des détails des appels sur plusieurs sites en une seule commande</span><span class="sxs-lookup"><span data-stu-id="d01fd-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="d01fd-128">Cette commande active l’enregistrement des détails des appels pour tous les paramètres de configuration de l’enregistrement des détails des appels utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d01fd-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

<span data-ttu-id="d01fd-129">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d01fd-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="d01fd-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d01fd-130">See also</span></span>

[<span data-ttu-id="d01fd-131">Planification de la surveillance</span><span class="sxs-lookup"><span data-stu-id="d01fd-131">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="d01fd-132">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="d01fd-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
