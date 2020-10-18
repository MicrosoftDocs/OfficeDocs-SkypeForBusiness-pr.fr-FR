---
title: 'Lync Server 2013 : utilisation des options de ligne de commande du programme d’installation'
description: 'Lync Server 2013 : utilisation des options de ligne de commande du programme d’installation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15c3490ead090766462ce83cb13ffe62355032cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580240"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="9e5b6-103">Utilisation des options de ligne de commande du programme d’installation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e5b6-103">Using Setup command-line options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e5b6-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9e5b6-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9e5b6-105">La ligne de commande Setup.exe est utilisée pour très peu d’opérations dans le programme d’installation d’Office.</span><span class="sxs-lookup"><span data-stu-id="9e5b6-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="9e5b6-106">Au lieu d’utiliser les options de ligne de commande du programme d’installation, vous utiliserez généralement l’outil de personnalisation Office et le fichier Config.xml pour la personnalisation des composants et de la configuration du produit.</span><span class="sxs-lookup"><span data-stu-id="9e5b6-106">Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="9e5b6-107">La ligne de commande Office Setup.exe reconnaît les options de ligne de commande décrites dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="9e5b6-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="9e5b6-108">Options d’installation d’Office Command-Line</span><span class="sxs-lookup"><span data-stu-id="9e5b6-108">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e5b6-109">Option de Command-Line de configuration</span><span class="sxs-lookup"><span data-stu-id="9e5b6-109">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="9e5b6-110">Description</span><span class="sxs-lookup"><span data-stu-id="9e5b6-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e5b6-111">/admin</span><span class="sxs-lookup"><span data-stu-id="9e5b6-111">/admin</span></span></p></td>
<td><p><span data-ttu-id="9e5b6-112">Exécute l’Outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).</span><span class="sxs-lookup"><span data-stu-id="9e5b6-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e5b6-113">/adminfile [chemin]</span><span class="sxs-lookup"><span data-stu-id="9e5b6-113">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="9e5b6-p102">Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.</span><span class="sxs-lookup"><span data-stu-id="9e5b6-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e5b6-116">/config [chemin]</span><span class="sxs-lookup"><span data-stu-id="9e5b6-116">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="9e5b6-117">Spécifie le fichier Config.xml que le programme d’installation utilise au cours de l’installation.</span><span class="sxs-lookup"><span data-stu-id="9e5b6-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="9e5b6-118">Utilisez l’option/config pour spécifier le fichier de Config.xml que vous avez personnalisé pour les installations de Lync 2013, par exemple : <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="9e5b6-118">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e5b6-119">/Modify Lync</span><span class="sxs-lookup"><span data-stu-id="9e5b6-119">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="9e5b6-120">Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante.</span><span class="sxs-lookup"><span data-stu-id="9e5b6-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="9e5b6-121">Par exemple, vous pouvez utiliser l’option/Modify pour ajouter ou supprimer des fonctionnalités Lync.</span><span class="sxs-lookup"><span data-stu-id="9e5b6-121">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e5b6-122">/Repair Lync</span><span class="sxs-lookup"><span data-stu-id="9e5b6-122">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="9e5b6-123">Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Lync.</span><span class="sxs-lookup"><span data-stu-id="9e5b6-123">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e5b6-124">/Uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="9e5b6-124">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="9e5b6-125">Exécute le programme d’installation pour supprimer Lync de l’ordinateur de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9e5b6-125">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9e5b6-126">Pour plus d’informations sur l’utilisation des options de ligne de commande du programme d’installation, voir <https://go.microsoft.com/fwlink/p/?linkid=267515> .</span><span class="sxs-lookup"><span data-stu-id="9e5b6-126">For details about using the setup command-line options, see <https://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

