---
title: Associer des rapports de surveillance à une base de données miroir dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Résumé : Découvrez comment associer des rapports de surveillance à une base de données miroir utilisée par Skype pour Business Server.'
ms.openlocfilehash: c598e8c14c5a592203501ca40264232ce344b2bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894534"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="5519f-103">Associer des rapports de surveillance à une base de données miroir dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="5519f-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="5519f-104">**Résumé :** Découvrez comment associer des rapports de surveillance avec une base de données miroir utilisée par Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="5519f-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="5519f-105">Rapports de surveillance avec une base de données miroir</span><span class="sxs-lookup"><span data-stu-id="5519f-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="5519f-106">Si vous configurez une instance miroir pour votre base de données de surveillance, cette base de données miroir prendra la relève en tant que base de données principale en cas de basculement.</span><span class="sxs-lookup"><span data-stu-id="5519f-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="5519f-107">Toutefois, si vous utilisez Skype pour les rapports de surveillance Business Server et un basculement se produit, vous trouverez que vos rapports de surveillance se connectent pas à la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="5519f-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="5519f-108">Et ce, car, lorsque vous installez des rapports de surveillance, vous spécifiez seulement l’emplacement de la base de données principale ; vous devez aussi spécifier l’emplacement de la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="5519f-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="5519f-p102">Pour que les rapports basculent automatiquement sur la base de données miroir, vous devez ajouter la base de données miroir comme « partenaire de basculement » pour les deux bases de données utilisées par les rapports de surveillance (l’une pour les données d’enregistrement des détails des appels, et l’autre pour les données de la qualité de l’expérience (QoE)). (Notez que cette étape doit être effectuée après l’installation des rapports de surveillance.) Vous pouvez ajouter les informations du partenaire de basculement en modifiant manuellement les valeurs des chaînes de connexion utilisées par ces deux bases de données. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5519f-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="5519f-p103">Utilisez Internet Explorer pour ouvrir la page d’accueil de **SQL Server Reporting Services**. L’URL de cette page d’accueil comprend ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="5519f-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="5519f-114">Le préfixe **http:**.</span><span class="sxs-lookup"><span data-stu-id="5519f-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="5519f-115">Le nom de domaine complet (FQDN) de l’ordinateur sur lequel les services de surveillance sont installés (par exemple, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="5519f-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="5519f-116">La chaîne de caractères **/Reports_**.</span><span class="sxs-lookup"><span data-stu-id="5519f-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="5519f-117">Le nom de l’instance de la base de données où les rapports de surveillance sont installés (par exemple, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="5519f-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="5519f-118">Par exemple, si SQL Server Reporting Services a été installé sur l’ordinateur atl-sql-001.litwareinc.com et que les rapports de surveillance utilisent l’instance de base de données archinst, l’URL de la page d’accueil doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="5519f-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="5519f-119">Après avoir accédé à la page d’accueil des services de surveillance, cliquez sur **ServerReports**, puis sur **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="5519f-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="5519f-120">Qui vous dirige vers la page **Reports_Content** pour le Skype pour les rapports de surveillance Business Server.</span><span class="sxs-lookup"><span data-stu-id="5519f-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="5519f-121">Sur la page **Reports_Content**, cliquez sur la source de données **CDRDB**.</span><span class="sxs-lookup"><span data-stu-id="5519f-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="5519f-p105">Sur la page **CDRDB**, sous l’onglet **Propriétés**, recherchez le texte intitulé **Chaîne de connexion**. La chaîne de connexion actuelle a un format similaire à celui-ci :</span><span class="sxs-lookup"><span data-stu-id="5519f-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="5519f-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="5519f-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="5519f-p106">Modifiez la chaîne de connexion façon à y inclure le nom du serveur et l’instance de base de données pour la base de données miroir. Par exemple, si le serveur est nommé atl-miroir-001 et que la base de données miroir est dans l’instance archinst, vous devez en plus spécifier la base de données miroir en utilisant cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="5519f-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="5519f-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="5519f-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="5519f-128">Votre chaîne de connexion modifiée ressemblera à ceci :</span><span class="sxs-lookup"><span data-stu-id="5519f-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="5519f-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="5519f-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="5519f-130">Après avoir mis à jour la chaîne de connexion, cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="5519f-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="5519f-p107">Sur la page **CDRDB**, cliquez sur le lien **Reports_Content**. Cliquez sur la source de données **QMSDB**, puis modifiez la chaîne de connexion pour la base de données QoE. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5519f-p107">On the **CDRDB** page, click the **Reports_Content** link. Click the **QMSDB** data source, and then edit the connection string for the QoE database. For example:</span></span>
    
    <span data-ttu-id="5519f-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="5519f-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="5519f-135">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="5519f-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5519f-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5519f-136">See also</span></span>

[<span data-ttu-id="5519f-137">Installer les rapports de surveillance dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="5519f-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="5519f-138">Utilisation des rapports de surveillance dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="5519f-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
