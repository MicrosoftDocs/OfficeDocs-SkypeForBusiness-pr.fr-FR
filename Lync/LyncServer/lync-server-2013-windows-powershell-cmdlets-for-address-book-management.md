---
title: 'Lync Server 2013 : applets de commande Windows PowerShell pour la gestion des carnets d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets for Address Book management
ms:assetid: 73bfa949-5628-4156-ad20-fe07a0dc6216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429708(v=OCS.15)
ms:contentKeyID: 48184512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170936c8ca4445a7dc4e816c2300176d9b730f80
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535321"
---
# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="ba810-102">Applets de commande Windows PowerShell pour les services de carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba810-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ba810-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ba810-104">Lync Server fournit un certain nombre d’applets de commande d’interface de ligne de commande Windows PowerShell pour gérer et configurer le service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="ba810-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="ba810-105">Certaines de ces applets de commande sont des remplacements pour les commandes ABServer.exe utilisées dans les versions précédentes d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="ba810-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="ba810-106">Les rubriques suivantes décrivent les applets de commande utilisées pour définir, créer et récupérer les informations relatives au service de carnet d’adresses et à sa configuration, ainsi que les informations relatives aux services web utilisés par le service de carnet d’adresses quand les clients récupèrent les fichiers et paramètres de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="ba810-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="ba810-107">Toutes ces applets de commande sont émises via Lync Server Management Shell dans les outils Lync Server sur un serveur ou une station de travail où les outils d’administration ont été installés.</span><span class="sxs-lookup"><span data-stu-id="ba810-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ba810-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ba810-108">In This Section</span></span>

  - [<span data-ttu-id="ba810-109">New-CsAddressBookConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="ba810-110">Set-CsAddressBookConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="ba810-111">Get-CsAddressBookConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="ba810-112">Remove-CsAddressBookConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="ba810-113">Test-CsAddressBookService pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="ba810-114">Test-CsAddressBookWebQuery pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="ba810-115">Update-CsAddressBook pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="ba810-116">New-CsClientPolicy pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="ba810-117">Set-CsClientPolicy pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="ba810-118">Get-CsService pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="ba810-119">New-CsWebServiceConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="ba810-120">Get-CsWebServiceConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="ba810-121">Set-CsWebServiceConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="ba810-122">Remove-CsWebServiceConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba810-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="ba810-123">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="ba810-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ba810-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba810-124">See Also</span></span>


[https://go.microsoft.com/fwlink/p/?linkId=205826](https://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

