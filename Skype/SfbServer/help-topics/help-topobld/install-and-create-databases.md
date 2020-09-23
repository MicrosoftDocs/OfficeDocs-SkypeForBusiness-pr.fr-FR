---
title: Installer et créer des bases de données
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement. Par défaut, la base de données est créée sur le serveur SQL Server défini dans le site défini et déploiera et configurera automatiquement les fichiers de base de données en fonction du serveur SQL Server sur lequel vous placez les bases de données.
ms.openlocfilehash: ade264fcda73df408f6bb323dd1e3733ccdd45f1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215385"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="66bfc-104">Installer et créer des bases de données</span><span class="sxs-lookup"><span data-stu-id="66bfc-104">Install and Create Databases</span></span>

<span data-ttu-id="66bfc-105">Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="66bfc-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="66bfc-106">Par défaut, la base de données est créée sur le serveur SQL Server défini dans le site défini et déploiera et configurera automatiquement les fichiers de base de données en fonction du serveur SQL Server sur lequel vous placez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="66bfc-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="66bfc-p103">**Sélectionnez les bases de données que vous souhaitez créer** : activez la case à cocher de toutes les bases de données que vous envisagez de déployer et de configurer. Activez la case à cocher de certaines ou de toutes les bases de données que vous déploierez.</span><span class="sxs-lookup"><span data-stu-id="66bfc-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="66bfc-109">Le serveur SQL Server doit déjà avoir été configuré pour l’instance (le cas échéant) et des ports de pare-feu doivent être ouverts pour accueillir l’instance sur laquelle vous déployez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="66bfc-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="66bfc-110">Pour plus d’informations, voir [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="66bfc-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="66bfc-111">**Avancé**: cliquez sur le serveur SQL, puis cliquez sur le bouton **avancé** pour choisir les options des emplacements des fichiers de base de données sur votre serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="66bfc-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="66bfc-112">Pour plus d’informations sur l’emplacement du fichier de base de données avancé, voir [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="66bfc-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="66bfc-113">**Précédent** : le fait de cliquer sur ce bouton vous permet de revenir à l’écran précédent (il n’est peut-être pas toujours disponible, selon la façon dont vous avez atteint cette boîte de dialogue).</span><span class="sxs-lookup"><span data-stu-id="66bfc-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="66bfc-114">**Suivant** : le fait de cliquer sur ce bouton valide votre sélection sur la boîte de dialogue active et vous permet d’accéder à la boîte de dialogue suivante pour configurer des informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="66bfc-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="66bfc-115">**Annuler** : le fait de cliquer sur ce bouton vous fera quitter cette étape de configuration et annulera vos modifications.</span><span class="sxs-lookup"><span data-stu-id="66bfc-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="66bfc-116">Certains écrans, mais pas tous, vous inviteront à quitter et à annuler vos modifications.</span><span class="sxs-lookup"><span data-stu-id="66bfc-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="66bfc-117">Si vous sélectionnez **Oui** , la configuration actuelle est fermée et la configuration actuelle est fermée et vous revenez au générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="66bfc-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="66bfc-118">En sélectionnant **Non**, vous reviendrez dans la boîte de dialogue active où vous pourrez poursuivre la configuration.</span><span class="sxs-lookup"><span data-stu-id="66bfc-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="66bfc-119">**Aide** : en cliquant sur le bouton **Aide**, vous affichez les informations d’aide associées à la boîte de dialogue de configuration active.</span><span class="sxs-lookup"><span data-stu-id="66bfc-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


