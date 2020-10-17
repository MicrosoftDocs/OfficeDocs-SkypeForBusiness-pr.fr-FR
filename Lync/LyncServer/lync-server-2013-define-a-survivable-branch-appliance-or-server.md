---
title: 'Lync Server 2013 : définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server'
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
ms.openlocfilehash: ee83a532f3e378cf0beb0d9d09a08e935cf56247
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516371"
---
# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a>Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-07_

Effectuez cette procédure sur le site central si vous n’avez pas défini le Survivable Branch Appliance ou le serveur Survivable Branch Server lorsque vous l’avez ajouté à votre topologie.

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a>Pour définir un Survivable Branch Appliance ou un serveur Survivable Branch Server

1.  Cliquez successivement sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologies Lync Server**.

2.  Dans l’arborescence de la console, développez le site central, développez **sites de succursale**, puis développez le nom du site de succursale où vous souhaitez déployer le Survivable Branch Appliance ou le serveur Survivable Branch Server.

3.  Cliquez avec le bouton droit sur **Survivable Branch Appliances**, puis cliquez sur **nouveau Survivable Branch Appliance**.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Survivable Branch Appliances</STRONG> est l’endroit où vous définissez les serveurs Survivable Branch Servers et les Survivable Branch Appliances.

    
    </div>

4.  Dans la boîte de dialogue **définir le Survivable Branch Appliance** , cliquez sur nom de domaine **complet**, tapez le nom de domaine complet (FQDN) du Survivable Branch Appliance ou du serveur Survivable Branch Server que vous allez déployer sur ce site de succursale, puis cliquez sur **suivant**.
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous définissez un Survivable Branch appliance, le nom que vous entrez dans le nom de <STRONG>domaine complet</STRONG> doit être le même que celui du Survivable Branch Appliance que vous avez affecté à l’attribut <STRONG>servicePrincipalName</STRONG> . Pour plus d’informations, consultez <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">la rubrique ajouter un Survivable Branch appliance à Active Directory dans Lync Server 2013</A>.

    
    </div>

5.  Cliquez sur **pool frontal**, cliquez sur le serveur frontal (pool de services d’utilisateurs) sur le site central auquel ce Survivable Branch Appliance ou le serveur Survivable Branch Server se connectera, puis cliquez sur **suivant**.

6.  Cliquez sur **serveur Edge**, cliquez sur le pool de serveurs Edge auquel ce Survivable Branch Appliance ou le serveur Survivable Branch Server se connectera pour fournir la connectivité PSTN aux utilisateurs distants du site de succursale, puis cliquez sur **suivant**.

7.  Cliquez sur **adresse IP ou nom de domaine complet**de la passerelle, puis tapez le nom de domaine complet ou l’adresse IP de l’homologue de passerelle auquel est associé le Survivable Branch Appliance ou le serveur Survivable Branch Server pour le routage des appels RTC entrants ou sortants.
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous définissez un Survivable Branch Appliance, il s’agit de la passerelle à laquelle le serveur de médiation qui se trouve à l’intérieur du Survivable Branch Appliance se connectera pour la connectivité PSTN.

    
    </div>

8.  Cliquez sur **Port d’écoute pour la passerelle IP/PSTN**, puis acceptez le port par défaut.

9.  Dans **protocole de transport SIP**, cliquez sur le protocole de transport que le Survivable Branch Appliance ou le serveur Survivable Branch utilisera, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous conseillons vivement d’utiliser le protocole TLS (Transport Layer Security). Si vous définissez un Survivable Branch Appliance, consultez la documentation du fournisseur de votre Survivable Branch Appliance pour vérifier que ce dernier prend en charge le protocole TLS.

    
    </div>

10. Dans l’arborescence de la console, cliquez avec le bouton droit sur le nouveau Survivable Branch Appliance ou serveur Survivable Branch Server, cliquez sur **Topologie**, puis sur **Publier**.

**Étape suivante**: [déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013-tâche de site de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

