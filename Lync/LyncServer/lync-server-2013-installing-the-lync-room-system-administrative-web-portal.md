---
title: 'Lync Server 2013 : installation du portail Web d’administration de Lync Room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af0f52b940e9bcfb78048ef3a2c60f09d265073
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="ffaf3-102">Installation du portail Web d’administration de Lync Room System dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffaf3-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffaf3-103">_**Dernière modification de la rubrique :** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="ffaf3-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="ffaf3-104">Vous pouvez télécharger le portail Web d’administration de Microsoft Lync Room System à partir du centre [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)de téléchargement Microsoft à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="ffaf3-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="ffaf3-105">Pour installer le portail Web d’administration de Lync Room System, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ffaf3-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="ffaf3-106">Configurez le port d’applications approuvées en exécutant l’applet de commande suivante dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="ffaf3-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="ffaf3-107">Pour installer le portail de salle de réunion, téléchargez **LyncRoomAdminPortal. exe** , puis exécutez-le en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="ffaf3-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="ffaf3-108">Ouvrez le fichier Web. config à partir de l’emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="ffaf3-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="ffaf3-109">% Program Files%\\Microsoft Lync Server 2013\\Web Components\\de la\\salle\\de réunion gestionnaire int du portail</span><span class="sxs-lookup"><span data-stu-id="ffaf3-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="ffaf3-110">Dans le fichier Web. config, remplacez PortalUserName par le nom d’utilisateur créé à l’étape 2 sous la section « Configuration des éléments prérequis pour le portail d’administration de Lync Room System » (le nom recommandé à l’étape est LRSApp) :</span><span class="sxs-lookup"><span data-stu-id="ffaf3-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="ffaf3-111">Étant donné que le portail d’administration LRS est une application approuvée, vous n’avez pas besoin de fournir le mot de passe dans la configuration du portail.</span><span class="sxs-lookup"><span data-stu-id="ffaf3-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="ffaf3-112">Si cet utilisateur utilise un autre bureau d’enregistrement que le serveur d’inscriptions local, vous devez spécifier le serveur d’inscriptions en ajoutant la ligne suivante dans le fichier Web. config :</span><span class="sxs-lookup"><span data-stu-id="ffaf3-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="ffaf3-113">Si le port utilisé n’est pas 5061, ajoutez la ligne suivante dans le fichier Web. config :</span><span class="sxs-lookup"><span data-stu-id="ffaf3-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="ffaf3-114">Vérification de l’installation du portail Web d’administration de Lync Room System</span><span class="sxs-lookup"><span data-stu-id="ffaf3-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="ffaf3-115">Pour vérifier l’installation du portail Web d’administration de Lync Room System, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ffaf3-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="ffaf3-116">Sur un serveur frontal, accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="ffaf3-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="ffaf3-117">https://\<serveur\>frontal/LRS</span><span class="sxs-lookup"><span data-stu-id="ffaf3-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="ffaf3-118">Vous ne devez pas voir les erreurs, comme illustré dans l’image suivante :</span><span class="sxs-lookup"><span data-stu-id="ffaf3-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="ffaf3-119">![Écran de connexion du portail d’administration Lync Room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Écran de connexion du portail d’administration Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="ffaf3-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="ffaf3-120">Si aucune erreur ne s’affiche, essayez d’accéder à l’URL suivante à partir de n’importe quel autre ordinateur de la topologie :</span><span class="sxs-lookup"><span data-stu-id="ffaf3-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="ffaf3-121">https://\<serveur\>frontal/LRS</span><span class="sxs-lookup"><span data-stu-id="ffaf3-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="ffaf3-122">Pour accéder à la page, vous devez ajouter les enregistrements DNS comme décrit dans la section « enregistrements DNS requis pour la connexion automatique des clients » [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="ffaf3-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

