---
title: Activation de l’enregistrement des détails des appels dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Résumé : Apprenez à activer les détails de l’appel d’enregistrement des enregistrements de (CDR) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 3fe33f3cfde310b3674c125b7eb8ab1bf04f7c03
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-detail-recording-in-skype-for-business-server-2015"></a><span data-ttu-id="2dd95-103">Activation de l’enregistrement des détails des appels dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="2dd95-103">Enable call detail recording in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2dd95-104">**Résumé :** Apprenez à activer les détails de l’appel d’enregistrement des enregistrements de (CDR) dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2dd95-104">**Summary:** Learn how to enable Call detail recording (CDR) records in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2dd95-p101">La fonctionnalité d’enregistrement des détails des appels recense des informations d’utilisation et de diagnostic sur les activités d’égal à égal, telles que la messagerie instantanée, les appels VoIP (Voice over Internet Protocol), le partage d’application, le transfert de fichiers et les réunions. Vous pouvez utiliser les données d’utilisation pour calculer le retour sur investissement (ROI) et les données de diagnostic pour résoudre les problèmes liés aux activités d’égal à égal et aux réunions.</span><span class="sxs-lookup"><span data-stu-id="2dd95-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> 
  
<span data-ttu-id="2dd95-107">Procédez comme suit pour activer l’enregistrement des détails des appels dans toute l’organisation ou dans chacun de ses sites.</span><span class="sxs-lookup"><span data-stu-id="2dd95-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2dd95-108">Pour activer l’enregistrement des détails des appels, vous devez configurer la surveillance et une base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="2dd95-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="2dd95-109">Pour plus d’informations, consultez [Déploiement de surveillance](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="2dd95-109">For details, see [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span> 
  
### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a><span data-ttu-id="2dd95-110">Pour activer des CD-r avec Skype pour Business Server du Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="2dd95-110">To enable CDR with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="2dd95-111">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou dispose de droits d’utilisateur équivalent), ou le rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur sur le réseau dans lequel vous avez déployé Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2dd95-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="2dd95-112">Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="2dd95-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2dd95-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="2dd95-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span> 
    
4. <span data-ttu-id="2dd95-114">Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans la table, sur **Action**, puis sur **Activer l’enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="2dd95-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2dd95-115">Cette fonctionnalité est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2dd95-115">CDR is enabled by default.</span></span> 
  
## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2dd95-116">L’activation de CD-r à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2dd95-116">Enabling CDR by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2dd95-117">Vous pouvez activer les CD-r à l’aide de Windows PowerShell et l’applet de commande **Set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2dd95-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="2dd95-118">Vous pouvez exécuter cette applet de commande depuis le Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2dd95-118">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2dd95-119">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter sur Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="2dd95-119">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="2dd95-120">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="2dd95-120">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="2dd95-121">Pour activer l’enregistrement des détails des appels pour un seul site</span><span class="sxs-lookup"><span data-stu-id="2dd95-121">To enable CDR for a single location</span></span>

 <span data-ttu-id="2dd95-122">Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur True ($True).</span><span class="sxs-lookup"><span data-stu-id="2dd95-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="2dd95-123">Pour désactiver l’enregistrement des détails des appels pour un seul site</span><span class="sxs-lookup"><span data-stu-id="2dd95-123">To disable CDR for a single location</span></span>

 <span data-ttu-id="2dd95-p104">Pour désactiver l’enregistrement des détails des appels, attribuez au paramètre EnableCDR la valeur False ($False). Cette désactivation n’a pas pour effet de désinstaller la surveillance ; il interrompt la collecte et le stockage des données d’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="2dd95-p104">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="2dd95-127">Pour activer l’enregistrement des détails des appels sur plusieurs sites en une seule commande</span><span class="sxs-lookup"><span data-stu-id="2dd95-127">To use a single command to enable CDR in multiple locations</span></span>

 <span data-ttu-id="2dd95-128">Cette commande active l’enregistrement des détails des appels pour tous les paramètres de configuration de l’enregistrement des détails des appels utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2dd95-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True
  ```

<span data-ttu-id="2dd95-129">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="2dd95-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2dd95-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2dd95-130">See also</span></span>

[<span data-ttu-id="2dd95-131">Planification du contrôle</span><span class="sxs-lookup"><span data-stu-id="2dd95-131">Planning for Monitoring</span></span>](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[<span data-ttu-id="2dd95-132">Déploiement de surveillance</span><span class="sxs-lookup"><span data-stu-id="2dd95-132">Deploying Monitoring</span></span>](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)