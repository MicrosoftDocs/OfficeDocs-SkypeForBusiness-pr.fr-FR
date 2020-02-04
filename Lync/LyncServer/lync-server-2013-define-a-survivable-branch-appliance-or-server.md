---
title: 'Lync Server 2013 : Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df5577ff0211afd005feb8fea4788598a03d536e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-07_

Suivez cette procédure sur le site central si vous n’avez pas défini l’appareil ou le serveur de succursale Survivable lorsque vous l’avez ajouté à votre topologie.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>Pour définir une unité de branchement ou un serveur de succursale survivant

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans l’arborescence de la console, développez le site central, développez **sites de succursales**, puis développez le nom du site de succursale dans lequel vous envisagez de déployer l’application de succursale ou le serveur de succursale Survivable.

3.  Cliquez avec le bouton droit sur **périphériques survivables**, puis cliquez sur **nouvelle unité de branchement Survivable**.
    
    <div>
    

    > [!IMPORTANT]  
    > Les <STRONG>appareils de branchement survivables</STRONG> vous permet de définir des serveurs de succursales survivables et des appareils de branchement plus survivant.

    
    </div>

4.  Dans la boîte de dialogue **définir une branche Survivable** , **cliquez sur**nom de domaine complet, tapez le nom de domaine complet (FQDN) de l’appareil ou du serveur de succursales survivant que vous déploierez sur ce site de succursale, puis cliquez sur **suivant**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous définissez une unité de branchement Survivable, le nom que vous entrez dans <STRONG>FQDN</STRONG> doit être le même que celui du nom de domaine complet (FQDN) <STRONG>de l’appareil</STRONG> . Pour plus d’informations, reportez-vous <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">à la rubrique ajouter une application de branchement survivant à Active Directory dans Lync Server 2013</A>.

    
    </div>

5.  Cliquez sur **pool frontal**, cliquez sur le serveur frontal (pool de services d’application) sur le site central pour lequel est connectée cette unité de branchement ou serveur de succursale Survivable, puis cliquez sur **suivant**.

6.  Cliquez sur **serveur de bord**, cliquez sur le pool de bords de l’appareil de succursales ou du serveur de succursales survivant qui sera connecté pour fournir une connectivité PSTN aux utilisateurs distants du site de succursale, puis cliquez sur **suivant**.

7.  Cliquez sur FQDN de la **passerelle ou adresse IP**, puis tapez le nom de domaine complet ou l’adresse IP de l’homologue de la passerelle pour le routage des appels RTC entrants ou sortants.
    
    <div>
    

    > [!IMPORTANT]  
    > S’il s’agit de la définition d’une unité de branchement survivant, il s’agit de la passerelle à laquelle le serveur de médiation de l’appareil de branchement survivant se connecte pour la connectivité PSTN.

    
    </div>

8.  Cliquez sur **port d’écoute pour la passerelle RTC/IP**, puis acceptez le port par défaut.

9.  Dans **protocole de transport SIP**, cliquez sur le protocole de transport utilisé par l’unité de branchement ou le serveur de succursales survivant, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous recommandons vivement d’utiliser le protocole TLS (Transport Layer Security). Si vous définissez une application branche Survivable, consultez la documentation fournie par le fabricant de votre appareil pour vérifier que votre application de branchement Survivable prend en charge le protocole TLS.

    
    </div>

10. Dans l’arborescence de la console, cliquez avec le bouton droit sur la nouvelle branche ou serveur Survivable, cliquez sur **Topology**, puis sur **publier**.

**Étape suivante**: [déploiement d’une unité ou d’un serveur de succursale Survivable avec Lync Server 2013-tâche de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

