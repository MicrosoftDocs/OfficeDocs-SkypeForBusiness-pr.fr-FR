---
title: 'Lync Server 2013 : Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc4eefe4c1ef804b1deb06d056bfbd61ade35eb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="a698a-102">Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a698a-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a698a-103">_**Dernière modification de la rubrique:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="a698a-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="a698a-104">Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a698a-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="a698a-105">Vous devez configurer un mot de passe sur le compte Kerberos de chaque site qui comporte des serveurs front-end, Standard Edition Server et Directors.</span><span class="sxs-lookup"><span data-stu-id="a698a-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="a698a-106">Vous pouvez configurer le mot de passe en exécutant l’applet de cmdlet Windows PowerShell **Set-CsKerberosAccountPassword** sur un serveur du site (par exemple, un serveur frontal).</span><span class="sxs-lookup"><span data-stu-id="a698a-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="a698a-107">Pour chaque site, vous devez exécuter l’applet de cmdlet **Set-CsKerberosAccountPassword** .</span><span class="sxs-lookup"><span data-stu-id="a698a-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="a698a-108">L’applet de contrôle configure Internet Information Services (IIS) pour le service de services Web, puis définit le mot de passe sur le compte d’ordinateur dans les services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a698a-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="a698a-109">Une autre méthode, en fonction du paramètre utilisé avec l’applet de passe, configure IIS sur un serveur lors de l’utilisation d’un autre serveur configuré comme source du mot de passe du compte Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a698a-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="a698a-110">Lorsque vous utilisez l’applet de cmdlet **Set-CsKerberosAccountPassword** pour définir un mot de passe, Kerberos définit le mot de passe sur une chaîne générée de manière aléatoire.</span><span class="sxs-lookup"><span data-stu-id="a698a-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="a698a-111">Cette applet de cmdlet contacte toutes les instances IIS dans tous les sites centraux Lync Server 2013 auxquels ce compte est attribué.</span><span class="sxs-lookup"><span data-stu-id="a698a-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="a698a-112">Pour définir un mot de passe pour un compte d’authentification Kerberos</span><span class="sxs-lookup"><span data-stu-id="a698a-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="a698a-113">Ouvrez une session sur n’importe quel ordinateur du domaine sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a698a-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="a698a-114">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a698a-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a698a-115">À partir de la ligne de commande, exécutez les deux commandes suivantes:</span><span class="sxs-lookup"><span data-stu-id="a698a-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="a698a-116">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a698a-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a698a-117">Vous devez spécifier le paramètre UserAccount en utilisant le format domaine\utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a698a-117">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="a698a-118">Le format user @ domain. extension n’est pas pris en charge pour référencer les objets ordinateur créés à des fins d’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a698a-118">The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a698a-119">Après avoir apporté des modifications à l’authentification Kerberos (par exemple, ajout d’un compte ou suppression d’un compte), vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a698a-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

