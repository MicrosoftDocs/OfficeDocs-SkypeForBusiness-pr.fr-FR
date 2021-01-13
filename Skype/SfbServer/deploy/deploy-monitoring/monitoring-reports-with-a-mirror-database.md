---
title: Associer des rapports de surveillance à une base de données miroir dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Résumé : Découvrez comment associer des rapports de surveillance à une base de données miroir utilisée par Skype Entreprise Server.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802164"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="a4d3e-103">Associer des rapports de surveillance à une base de données miroir dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a4d3e-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="a4d3e-104">**Résumé :** Découvrez comment associer des rapports de surveillance à une base de données miroir utilisée par Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="a4d3e-105">Surveiller les rapports avec une base de données miroir</span><span class="sxs-lookup"><span data-stu-id="a4d3e-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="a4d3e-106">Si vous configurez un miroir pour votre base de données de surveillance, cette base de données miroir prendra le relais en tant que base de données primaire en cas de failover.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="a4d3e-107">Toutefois, si vous utilisez les rapports de surveillance de Skype Entreprise Server et qu’un échec se produit, il se peut que vous trouviez que vos rapports de surveillance ne se connectent pas à la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="a4d3e-108">En effet, lorsque vous installez les rapports de surveillance, vous spécifiez uniquement l’emplacement de la base de données principale . vous ne spécifiez pas l’emplacement de la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="a4d3e-109">Pour que les rapports de surveillance soient automatiquement mis à jour vers la base de données miroir, vous devez ajouter la base de données miroir en tant que « partenaire deover » aux deux bases de données utilisées par les rapports de surveillance (une base de données pour les données d’enregistrement des détails des appels et l’autre pour les données de qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="a4d3e-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="a4d3e-110">(Notez que cette étape doit être effectuée après l’installation des rapports de surveillance.) Vous pouvez ajouter les informations du partenaire deover en éditant manuellement les valeurs de chaîne de connexion utilisées par ces deux bases de données.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="a4d3e-111">Pour ce faire, procédez de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="a4d3e-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="a4d3e-112">Utilisez Internet Explorer pour ouvrir la page **d’SQL Server Reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="a4d3e-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="a4d3e-113">L’URL de la page d’accueil reporting Services inclut :</span><span class="sxs-lookup"><span data-stu-id="a4d3e-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="a4d3e-114">**Préfixe http:**</span><span class="sxs-lookup"><span data-stu-id="a4d3e-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="a4d3e-115">Nom de domaine complet (FQDN) de l’ordinateur sur lequel Reporting Services est installé (par exemple, **atl-sql-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="a4d3e-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="a4d3e-116">Chaîne de **caractères /Reports_**.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="a4d3e-117">Nom de l’instance de base de données où les rapports de surveillance sont installés (par exemple, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="a4d3e-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="a4d3e-118">Par exemple, si SQL Server Reporting Services a été installé sur l’ordinateur atl-sql-001.litwareinc.com et que les rapports de surveillance utilisent l’instance de base de données archinst, l’URL de la page d’accueil ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="a4d3e-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="a4d3e-119">Une fois que vous avez accédé à la page d’accueil de Reporting Services, cliquez sur **ServerReports,** puis cliquez **sur Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="a4d3e-120">Cela vous permettra **d’Reports_Content** la page des rapports de surveillance de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="a4d3e-121">Dans la page **Reports_Content,** cliquez sur la source de données **CDRDB.**</span><span class="sxs-lookup"><span data-stu-id="a4d3e-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="a4d3e-122">Dans la page **CDRDB, sous** l’onglet **Propriétés,** recherchez la zone de texte « **Chaîne de connexion**».</span><span class="sxs-lookup"><span data-stu-id="a4d3e-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="a4d3e-123">La chaîne de connexion actuelle ressemblera à ceci :</span><span class="sxs-lookup"><span data-stu-id="a4d3e-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="a4d3e-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="a4d3e-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="a4d3e-125">Modifiez la chaîne de connexion pour inclure le nom du serveur et l’instance de base de données pour la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="a4d3e-126">Par exemple, si le serveur est nommé atl-mirror-001 et que la base de données miroir se trouve dans l’instance archinst, vous devez ajouter pour spécifier la base de données miroir à l’aide de cette syntaxe :</span><span class="sxs-lookup"><span data-stu-id="a4d3e-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="a4d3e-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="a4d3e-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="a4d3e-128">Votre chaîne de connexion modifiée ressemblera à ceci :</span><span class="sxs-lookup"><span data-stu-id="a4d3e-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="a4d3e-129">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="a4d3e-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="a4d3e-130">Après avoir mis à jour la chaîne de connexion, cliquez sur **Appliquer.**</span><span class="sxs-lookup"><span data-stu-id="a4d3e-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="a4d3e-131">Dans la page **CDRDB,** cliquez sur **Reports_Content** lien.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="a4d3e-132">Cliquez sur la source de **données QMSDB,** puis modifiez la chaîne de connexion pour la base de données QoE.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="a4d3e-133">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a4d3e-133">For example:</span></span>
    
    <span data-ttu-id="a4d3e-134">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="a4d3e-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="a4d3e-135">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="a4d3e-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a4d3e-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4d3e-136">See also</span></span>

[<span data-ttu-id="a4d3e-137">Installer des rapports de surveillance dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a4d3e-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="a4d3e-138">Utilisation des rapports de surveillance dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a4d3e-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
