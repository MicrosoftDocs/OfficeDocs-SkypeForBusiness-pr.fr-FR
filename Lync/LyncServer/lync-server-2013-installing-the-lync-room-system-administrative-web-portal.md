---
title: 'Lync Server 2013 : installation du portail Web d’administration du système de salle Lync'
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
ms.openlocfilehash: dcfc78429ef021afcb0ed286ad86a39e63bfbf62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="79a70-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79a70-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79a70-103">_**Dernière modification de la rubrique :** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="79a70-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="79a70-104">Vous pouvez télécharger le portail Web d’administration du système de salle Microsoft Lync à partir du [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79a70-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="79a70-105">Pour installer le portail Web d’administration du système de salle Lync, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="79a70-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="79a70-106">Configurez le port d’application fiable en exécutant l’applet de commande suivante dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="79a70-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="79a70-107">Pour installer le portail de salle de réunion, téléchargez **LyncRoomAdminPortal. exe** , puis exécutez-le en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="79a70-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="79a70-108">Ouvrez le fichier Web.config à partir de l’emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="79a70-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="79a70-109">% Program Files%\\Microsoft Lync Server 2013\\composants\\WebPart réunion portail\\\\de salle de réunion</span><span class="sxs-lookup"><span data-stu-id="79a70-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="79a70-110">Dans le fichier Web. config, remplacez PortalUserName par le nom d’utilisateur créé à l’étape 2 de la section « Configuration des conditions préalables pour le portail d’administration du système de salle Lync » (le nom recommandé pour l’étape est LRSApp) :</span><span class="sxs-lookup"><span data-stu-id="79a70-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="79a70-111">Le portail d’administration LRS étant une application fiable, vous n’avez pas besoin de fournir le mot de passe dans la configuration du portail.</span><span class="sxs-lookup"><span data-stu-id="79a70-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="79a70-112">Si cet utilisateur utilise un autre serveur d’inscriptions que le serveur d’inscriptions local, vous devez le spécifier en ajoutant la ligne suivante dans le fichier Web.Config :</span><span class="sxs-lookup"><span data-stu-id="79a70-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="79a70-113">Si le port utilisé n’est pas le port 5061, ajoutez la ligne suivante dans le fichier Web.Config : </span><span class="sxs-lookup"><span data-stu-id="79a70-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="79a70-114">Vérification de l’installation du portail Web d’administration du système de salle Lync</span><span class="sxs-lookup"><span data-stu-id="79a70-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="79a70-115">Pour vérifier l’installation du portail Web d’administration du système de salle Lync, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="79a70-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="79a70-116">Sur un serveur frontal, accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="79a70-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="79a70-117">https://\<Fe-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="79a70-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="79a70-118">Aucune erreur ne doit s’afficher, comme dans l’image suivante :</span><span class="sxs-lookup"><span data-stu-id="79a70-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="79a70-119">![Écran Connexion au portail d’administration Lync Room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Écran Connexion au portail d’administration Lync Room System")</span><span class="sxs-lookup"><span data-stu-id="79a70-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="79a70-120">Si aucune erreur ne s’affiche, essayez d’accéder à l’URL suivante à partir d’un autre ordinateur dans la topologie :</span><span class="sxs-lookup"><span data-stu-id="79a70-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="79a70-121">https://\<Fe-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="79a70-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="79a70-122">Pour accéder à la page, vous devez ajouter les enregistrements DNS comme décrit dans la section « enregistrements DNS requis pour la connexion automatique au [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)client ».</span><span class="sxs-lookup"><span data-stu-id="79a70-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

