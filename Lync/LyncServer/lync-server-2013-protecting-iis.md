---
title: 'Lync Server 2013 : protection des services Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d53797c490ba53872786311b51e310e6400addf5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="56a80-102">Protection des services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56a80-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56a80-103">_**Dernière modification de la rubrique :** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="56a80-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="56a80-104">Dans Microsoft Office Communications Server 2007 et Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) s’est exécuté sous un compte d’utilisateur standard.</span><span class="sxs-lookup"><span data-stu-id="56a80-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="56a80-105">Cela était susceptible de provoquer des problèmes : si ce mot de passe a expiré, vous pouviez perdre vos services Web, un problème souvent difficile à diagnostiquer.</span><span class="sxs-lookup"><span data-stu-id="56a80-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="56a80-106">Pour éviter le problème d’expiration des mots de passe, Microsoft Lync Server 2013 vous permet de créer un compte d’ordinateur (pour un ordinateur qui n’existe pas réellement) qui peut servir de principal d’authentification pour tous les ordinateurs d’un site qui exécutent les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="56a80-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="56a80-107">Étant donné que ces comptes utilisent le protocole d’authentification Kerberos, les comptes sont appelés comptes Kerberos et le nouveau processus d’authentification est appelé authentification Web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="56a80-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="56a80-108">Cela vous permet de gérer tous vos serveurs IIS à l’aide d’un seul compte.</span><span class="sxs-lookup"><span data-stu-id="56a80-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="56a80-109">Pour pouvoir exécuter vos serveurs sous ce nom principal d’authentification, vous devez créer un compte d’ordinateur au moyen de l’applet de commande New-CsKerberosAccount, le compte étant ensuite affecté à un ou plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="56a80-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="56a80-110">Une fois l’affectation effectuée, l’association entre le compte et le site Lync Server 2013 est activée en exécutant la cmdlet Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="56a80-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="56a80-111">Entre autres choses, cela crée le nom de principal du service (SPN) requis dans les services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="56a80-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="56a80-112">Les noms SPN permettent aux applications clientes de localiser un service.</span><span class="sxs-lookup"><span data-stu-id="56a80-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="56a80-113">Pour plus d’informations, consultez la rubrique [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="56a80-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="56a80-114">Meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="56a80-114">Best Practices</span></span>

<span data-ttu-id="56a80-p103">Pour aider à améliorer la sécurité d’IIS, nous vous recommandons d’implémenter un compte Kerberos pour IIS. Si vous ne le faites pas, IIS est exécuté sous un compte utilisateur standard.</span><span class="sxs-lookup"><span data-stu-id="56a80-p103">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS. If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

