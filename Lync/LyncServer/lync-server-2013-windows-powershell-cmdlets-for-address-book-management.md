---
title: 'Lync Server 2013 : cmdlets Windows PowerShell pour la gestion du carnet d’adresses'
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
ms.openlocfilehash: 5ec10f3e3d3d58a790ddc60fd1af1d1b09765685
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-for-address-book-services-in-lync-server-2013"></a><span data-ttu-id="8b39a-102">Cmdlets Windows PowerShell pour les services de carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-102">Windows PowerShell cmdlets for Address Book Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b39a-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8b39a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8b39a-104">Lync Server fournit un certain nombre d’applets de commande d’interface de ligne de commande Windows PowerShell pour gérer et configurer le service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="8b39a-104">Lync Server provides a number of Windows PowerShell command-line interface cmdlets to manage and configure the Address Book service.</span></span> <span data-ttu-id="8b39a-105">Certaines de ces applets de commande sont des remplacements des commandes ABServer. exe utilisées dans les versions précédentes d’Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="8b39a-105">Some of these cmdlets are replacements for the ABServer.exe commands used in previous versions of Office Communications Server.</span></span> <span data-ttu-id="8b39a-106">Les rubriques suivantes sont les applets de commande qui sont utilisées pour définir, créer et extraire des informations sur le service de carnet d’adresses, la configuration et les informations sur les services Web utilisés par le service de carnet d’adresses lorsque les clients récupèrent le service de carnet d’adresses fichiers et paramètres.</span><span class="sxs-lookup"><span data-stu-id="8b39a-106">In the following topics are the cmdlets that are used to set, create, and retrieve information about the Address Book service, its configuration and information about the Web services that the Address Book service uses when clients retrieve Address Book service files and settings.</span></span>

<span data-ttu-id="8b39a-107">Toutes ces applets de applet sont émises par le biais de Lync Server Management Shell, qui se trouve dans les outils Lync Server sur un serveur ou une station de travail sur lequel les outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="8b39a-107">All of these cmdlets are issued through the Lync Server Management Shell found in the Lync Server tools on a server or workstation where the administration tools have been installed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8b39a-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8b39a-108">In This Section</span></span>

  - [<span data-ttu-id="8b39a-109">Nouveauté-CsAddressBookConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-109">New-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsAddressBookConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-110">Set-CsAddressBookConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-110">Set-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-111">Get-CsAddressBookConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-111">Get-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-112">Remove-CsAddressBookConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-112">Remove-CsAddressBookConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-csaddressbookconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-113">Test-CsAddressBookService pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-113">Test-CsAddressBookService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookservice-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-114">Test-CsAddressBookWebQuery pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-114">Test-CsAddressBookWebQuery for Address Book management in Lync Server 2013</span></span>](lync-server-2013-test-csaddressbookwebquery-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-115">Update-CsAddressBook pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-115">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>](lync-server-2013-update-csaddressbook-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-116">Nouveauté-CsClientPolicy pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-116">New-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-new-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-117">Set-CsClientPolicy pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-117">Set-CsClientPolicy for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-csclientpolicy-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-118">Get-CsService pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-118">Get-CsService for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-csservice-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-119">Nouveauté-CsWebServiceConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-119">New-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-New-CsWebServiceConfiguration-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-120">Get-CsWebServiceConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-120">Get-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-get-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-121">Set-CsWebServiceConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-121">Set-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-set-cswebserviceconfiguration-for-address-book-management.md)

  - [<span data-ttu-id="8b39a-122">Remove-CsWebServiceConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b39a-122">Remove-CsWebServiceConfiguration for Address Book management in Lync Server 2013</span></span>](lync-server-2013-remove-cswebserviceconfiguration-for-address-book-management.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="8b39a-123">Sections associées</span><span class="sxs-lookup"><span data-stu-id="8b39a-123">Related Sections</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b39a-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b39a-124">See Also</span></span>


[http://go.microsoft.com/fwlink/p/?linkId=205826](http://go.microsoft.com/fwlink/p/?linkid=205826)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

