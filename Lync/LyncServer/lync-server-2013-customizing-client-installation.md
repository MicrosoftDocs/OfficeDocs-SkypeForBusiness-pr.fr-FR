---
title: 'Lync Server 2013 : personnalisation de l’installation du client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 755a53b6afc089093f5efbfd2a90699e12e66b8f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516691"
---
# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="6c516-102">Personnalisation de l’installation du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c516-102">Customizing client installation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c516-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="6c516-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="6c516-104">Les administrateurs d’entreprise peuvent personnaliser l’installation d’Office 2013 basée sur Windows Installer (. msi) à l’aide des méthodes décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="6c516-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="6c516-105">Étant donné qu’aucun outil unique ne fournit toutes les options de personnalisation, vous utiliserez probablement une combinaison de ces méthodes dans votre déploiement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6c516-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="6c516-106">Au minimum, vous pouvez utiliser les outils décrits dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="6c516-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="6c516-107">[Utilisation de l’outil de personnalisation Office (OPO) dans Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) pour personnaliser les options et les fonctionnalités d’installation de Lync et d’autres programmes Office.</span><span class="sxs-lookup"><span data-stu-id="6c516-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="6c516-108">[Utilisation de Config.xml pour effectuer des tâches d’installation dans Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) pour spécifier le chemin d’accès au point d’installation réseau et effectuer une installation sans assistance.</span><span class="sxs-lookup"><span data-stu-id="6c516-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="6c516-109">[Utilisation des options de ligne de commande du programme d’installation dans Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) pour spécifier le fichier Config.xml à utiliser lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="6c516-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="6c516-110">[Configuration des stratégies de démarrage client dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) à l’aide du composant logiciel enfichable MMC éditeur d’objets de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="6c516-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="6c516-p102">À mesure que vous déployez la suite de produits Office, il est probable que vous souhaitiez configurer d’autres options. Les rubriques de cette section vous donnent un aperçu de ces outils de personnalisation et traitent des considérations propres à Lync. Vous trouverez également des liens vers l’aide détaillée d’Office pour chaque outil.</span><span class="sxs-lookup"><span data-stu-id="6c516-p102">There will probably be other options you’ll want to configure as you deploy the Office suite of products. The topics in this section give an overview of these customization tools and discuss Lync-specific considerations. Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

