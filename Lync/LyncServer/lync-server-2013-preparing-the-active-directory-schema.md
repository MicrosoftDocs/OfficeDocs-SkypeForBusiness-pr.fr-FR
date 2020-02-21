---
title: 'Lync Server 2013 : préparation du schéma Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efabd082fce4dba5cf210e2c0f9c390324474cd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="47492-102">Préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47492-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47492-103">_**Dernière modification de la rubrique :** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="47492-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="47492-104">Avant de commencer à préparer les services de domaine Active Directory, vous pouvez ouvrir les fichiers de schéma à l’aide d’un éditeur de texte, tel que le bloc-notes Windows, ou consulter les [attributs, les classes et les extensions de schéma Active Directory utilisés par Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) pour examiner toutes les extensions de schéma des services de domaine Active Directory qui seront modifiées pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47492-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="47492-105">Lync Server utilise quatre fichiers de schéma :</span><span class="sxs-lookup"><span data-stu-id="47492-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="47492-106">ExternalSchema. ldf, qui est utilisé pour l’interopérabilité avec Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="47492-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="47492-107">ServerSchema. ldf, qui est le fichier de schéma Lync Server 2013 principal</span><span class="sxs-lookup"><span data-stu-id="47492-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="47492-108">BackCompatSchema.ldf, qui est utilisé pour l’interopérabilité avec des composants de versions précédentes</span><span class="sxs-lookup"><span data-stu-id="47492-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="47492-109">VersionSchema.ldf, qui est utilisé pour les informations de version du schéma préparé</span><span class="sxs-lookup"><span data-stu-id="47492-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="47492-110">Tous les fichiers .ldf sont installés au cours de la préparation du schéma, même si vous procédez à une migration depuis une version précédente ou à une nouvelle installation.</span><span class="sxs-lookup"><span data-stu-id="47492-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="47492-111">Ces fichiers de schéma sont installés dans l’ordre indiqué dans la liste précédente et se trouvent dans \\le\\dossier de schéma de prise en charge sur le support d’installation.</span><span class="sxs-lookup"><span data-stu-id="47492-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="47492-112">Les extensions de schéma Lync Server sont répliquées dans tous les domaines, ce qui a un impact sur le trafic réseau.</span><span class="sxs-lookup"><span data-stu-id="47492-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="47492-113">Exécutez la préparation du schéma lorsque l’utilisation du réseau est basse.</span><span class="sxs-lookup"><span data-stu-id="47492-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47492-114">Si vous devez ajouter la prise en charge pour les clients mobiles Microsoft® Office Communicator 2007 mobile R2 pour Java et Microsoft® Office Communicator Mobile pour Nokia 1,0 à votre déploiement Lync Server 2013, vous devez préparer le schéma Active Directory pour Microsoft Office Communications Server 2007 R2 lors de l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47492-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="47492-115">Pour obtenir les logiciels et la documentation nécessaires <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>, reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="47492-115">For the necessary software and documentation, see <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="47492-116">Éditeur ADSI</span><span class="sxs-lookup"><span data-stu-id="47492-116">ADSI Edit</span></span>

<span data-ttu-id="47492-117">L’Éditeur ADSI (Active Directory Service Interfaces) est un outil d’administration AD DS qui vous permet de vérifier la préparation et la réplication du schéma.</span><span class="sxs-lookup"><span data-stu-id="47492-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="47492-118">L’Éditeur ADSI est installé par défaut lorsque vous installez le rôle AD DS pour faire d’un serveur un contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="47492-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="47492-119">Pour Windows Server 2008 et Windows Server 2008 R2, ADSI Edit (adsiedit. msc) est inclus dans les outils d’administration de serveur distant (RSAT).</span><span class="sxs-lookup"><span data-stu-id="47492-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="47492-120">Vous pouvez également installer les outils d’administration de serveur distant sur des serveurs membres du domaine ou des serveurs autonomes.</span><span class="sxs-lookup"><span data-stu-id="47492-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="47492-121">Le package des outils d’administration de serveur distant est copié par défaut sur ces serveurs lorsque vous installez Windows, mais il n’est pas installé par défaut.</span><span class="sxs-lookup"><span data-stu-id="47492-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="47492-122">Utilisez le Gestionnaire de serveur pour installer chaque outil.</span><span class="sxs-lookup"><span data-stu-id="47492-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="47492-123">L’éditeur ADSI est inclus sous **Outils d’administration de rôles**, **Outils des services de domaine Active Directory**, **Outils de contrôleur de domaine Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="47492-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="47492-124">Pour Windows Server 2003, l’Éditeur ADSI fait partie des outils de support.</span><span class="sxs-lookup"><span data-stu-id="47492-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="47492-125">Les outils de support sont disponibles à partir du CD-ROM Windows \\Server\\2003 dans le dossier des outils de support, ou vous pouvez les télécharger à partir de « Windows server 2003 Service [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770)Pack 2 32-bit Support Tools » sur le site.</span><span class="sxs-lookup"><span data-stu-id="47492-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="47492-126">Les instructions d’installation des outils de support à partir du CD-ROM du produit sont disponibles à l' [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771)adresse « installer les outils de support Windows » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="47492-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="47492-127">Adsiedit.dll est inscrit automatiquement lorsque vous installez les outils de support.</span><span class="sxs-lookup"><span data-stu-id="47492-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="47492-128">Toutefois, si vous avez copié les fichiers sur votre ordinateur, vous devez exécuter la commande **regsvr32** pour inscrire le fichier adsiedit.dll avant de pouvoir exécuter l’outil.</span><span class="sxs-lookup"><span data-stu-id="47492-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47492-129">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="47492-129">In This Section</span></span>

  - [<span data-ttu-id="47492-130">Exécution de la préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47492-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="47492-131">Vérification de la réplication de schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47492-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47492-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47492-132">See Also</span></span>


[<span data-ttu-id="47492-133">Préparation de la forêt pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47492-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="47492-134">Préparation des domaines pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47492-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

