---
title: 'Lync Server 2013 : Création d’un compte d’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="22408-102">Création d’un compte d’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22408-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22408-103">_**Dernière modification de la rubrique:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="22408-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="22408-104">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="22408-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="22408-105">Vous pouvez créer des comptes d’authentification Kerberos pour chaque site, ou vous pouvez créer un compte d’authentification Kerberos unique et l’utiliser pour tous les sites.</span><span class="sxs-lookup"><span data-stu-id="22408-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="22408-106">Les applets de cmdlet Windows PowerShell vous permettent de créer et de gérer les comptes, y compris l’identification des comptes attribués à chaque site.</span><span class="sxs-lookup"><span data-stu-id="22408-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="22408-107">Le générateur de topologie et le panneau de configuration de Lync Server 2013 n’affichent pas de comptes d’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="22408-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="22408-108">Utilisez la procédure suivante pour créer un ou plusieurs comptes d’utilisateur à utiliser pour l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="22408-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="22408-109">Pour créer un compte Kerberos</span><span class="sxs-lookup"><span data-stu-id="22408-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="22408-110">En tant que membre du groupe Domain Admins, connectez-vous à un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="22408-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="22408-111">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="22408-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="22408-112">À partir de la ligne de commande, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="22408-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="22408-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="22408-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="22408-114">Vérifiez que l’objet ordinateur a été créé en ouvrant utilisateurs et ordinateurs Active Directory, développez le conteneur **utilisateurs** , puis vérifiez que l’objet ordinateur du compte d’utilisateur est dans le conteneur.</span><span class="sxs-lookup"><span data-stu-id="22408-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

