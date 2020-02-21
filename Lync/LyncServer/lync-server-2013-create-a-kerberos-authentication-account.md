---
title: 'Lync Server 2013 : création d’un compte d’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b41a19a46a23d24a680b3987f7d5eca01daab89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="53f08-102">Créer un compte d’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53f08-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53f08-103">_**Dernière modification de la rubrique :** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="53f08-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="53f08-104">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe Admins du domaine.</span><span class="sxs-lookup"><span data-stu-id="53f08-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="53f08-105">Vous pouvez créer des comptes d’authentification Kerberos pour chaque site, ou vous pouvez créer un seul compte d’authentification Kerberos et l’utiliser pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="53f08-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="53f08-106">Vous utilisez les applets de commande Windows PowerShell pour créer et gérer les comptes, y compris l’identification des comptes affectés à chaque site.</span><span class="sxs-lookup"><span data-stu-id="53f08-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="53f08-107">Le générateur de topologie et le panneau de configuration Lync Server 2013 n’affichent pas les comptes d’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="53f08-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="53f08-108">Suivez la procédure ci-après pour créer un ou plusieurs comptes d’utilisateur pour l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="53f08-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="53f08-109">Pour créer un compte Kerberos</span><span class="sxs-lookup"><span data-stu-id="53f08-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="53f08-110">En tant que membre du groupe administrateurs du domaine, ouvrez une session sur un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="53f08-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="53f08-111">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="53f08-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="53f08-112">Depuis la ligne de commande , exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="53f08-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="53f08-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="53f08-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="53f08-114">Vérifiez que l’objet Ordinateur a été créé en ouvrant Utilisateurs et ordinateurs Active Directory, développez le conteneur **Utilisateurs**, puis vérifiez que l’objet Ordinateur du compte d’utilisateur se trouve dans le conteneur.</span><span class="sxs-lookup"><span data-stu-id="53f08-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

