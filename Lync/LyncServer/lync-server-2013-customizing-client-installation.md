---
title: 'Lync Server 2013 : personnalisation de l’installation d’un client'
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
ms.openlocfilehash: ce9491e48d107d01f86d18e8154331ef3ae7e478
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="eb534-102">Personnalisation de l’installation du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb534-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb534-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="eb534-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="eb534-104">Les administrateurs d’entreprise peuvent personnaliser l’installation d’Office 2013 de Windows Installer (. msi) en utilisant les méthodes décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="eb534-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="eb534-105">Dans la mesure où il n’y a pas d’options de personnalisation, l’outil peut utiliser une combinaison de ces méthodes dans votre déploiement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="eb534-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="eb534-106">Au minimum, vous pouvez utiliser les outils décrits dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="eb534-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="eb534-107">[À l’aide de l’outil de personnalisation Office (OPO) dans Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) pour personnaliser les options et fonctionnalités de configuration pour Lync et d’autres programmes Office.</span><span class="sxs-lookup"><span data-stu-id="eb534-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="eb534-108">[L’utilisation de config. xml pour effectuer des tâches d’installation dans Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) pour spécifier le chemin d’accès du point d’installation réseau et effectuer une installation silencieuse.</span><span class="sxs-lookup"><span data-stu-id="eb534-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="eb534-109">Vous pouvez utiliser les [options de la ligne de commande du programme d’installation dans Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) pour spécifier le fichier config. XML à utiliser lors de l’installation.</span><span class="sxs-lookup"><span data-stu-id="eb534-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="eb534-110">[Configuration des stratégies de démarrage de clients dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) à l’aide du composant logiciel enfichable Éditeur d’objets de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="eb534-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="eb534-111">Lors du déploiement de la suite de produits Office, il est probable que vous souhaitiez configurer d’autres options.</span><span class="sxs-lookup"><span data-stu-id="eb534-111">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="eb534-112">Les rubriques de cette section donnent un aperçu de ces outils de personnalisation et présentent des considérations spécifiques à Lync.</span><span class="sxs-lookup"><span data-stu-id="eb534-112">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="eb534-113">Vous trouverez également des liens vers l’aide détaillée d’Office pour chaque outil.</span><span class="sxs-lookup"><span data-stu-id="eb534-113">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

