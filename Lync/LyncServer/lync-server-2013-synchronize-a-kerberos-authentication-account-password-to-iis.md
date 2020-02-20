---
title: Synchronisation d’un mot de passe de compte d’authentification Kerberos avec IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 255c1035809b69d5de1bb5e08fc770dc9a6b1c4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="86b7f-102">Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b7f-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86b7f-103">_**Dernière modification de la rubrique :** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="86b7f-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="86b7f-104">Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="86b7f-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="86b7f-105">Dans un site, les serveurs frontaux, les serveurs Standard Edition et les directeurs peuvent utiliser un compte d’authentification Kerberos à des fins d’authentification des demandes auprès du service Web.</span><span class="sxs-lookup"><span data-stu-id="86b7f-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="86b7f-106">Cette procédure localise chaque serveur exécutant des services Web dans un site auquel a été affecté un compte Kerberos et met à jour les paramètres de configuration des services Internet (IIS) pour utiliser le compte Kerberos.</span><span class="sxs-lookup"><span data-stu-id="86b7f-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="86b7f-107">Pour plus d’informations, reportez-vous à [la rubrique définir un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span><span class="sxs-lookup"><span data-stu-id="86b7f-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="86b7f-108">Pour définir et configurer un mot de passe de compte d’authentification Kerberos</span><span class="sxs-lookup"><span data-stu-id="86b7f-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="86b7f-109">Ouvrez une session sur un ordinateur source (tel que fe01.contoso.com) en tant que membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="86b7f-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="86b7f-110">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="86b7f-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="86b7f-111">À partir de la ligne de commande Lync Server Management Shell, exécutez les deux commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="86b7f-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="86b7f-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="86b7f-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="86b7f-p102">Le nom de l’ordinateur source et celui de l’ordinateur de destination doivent être un nom de domaine complet du serveur. Vous ne pouvez pas utiliser le nom de domaine complet du pool sauf si le nom du pool est le même que celui de l’ordinateur que vous utilisez comme ordinateur source ou ordinateur de destination.</span><span class="sxs-lookup"><span data-stu-id="86b7f-p102">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server. You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="86b7f-115">Après avoir apporté des modifications à l’authentification Kerberos, telles que l’ajout d’un compte ou la suppression d’un compte, vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="86b7f-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

