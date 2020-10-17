---
title: 'Lync Server 2013 : création d’une stratégie de site pour la conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0762a7a74e8a88c2ca67e78e5cf2a9f1b032fa15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501871"
---
# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a>Créer une stratégie de site pour la conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente propre au site.

La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie.

<div>


> [!NOTE]  
> Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Pour configurer les paramètres de configuration du serveur de conversation permanente, voir <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurer les options de serveur de conversation permanente globalement ou pour le pool de serveurs de conversation permanente dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Pour créer une stratégie de conversation permanente pour un site

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent Chat Server by Using Windows PowerShell Cmdlets</A> dans la documentation de déploiement.

    
    </div>

4.  Cliquez sur **Nouveau**, puis sur **Stratégie de site**.

5.  Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.

6.  Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, Redmond).
    
      - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de salle de conversation pour Redmond).
    
      - Pour contrôler la conversation permanente pour tous les sites qui ne sont pas spécifiquement contrôlés via une stratégie de site, activez ou désactivez la case à cocher **activer la conversation permanente** .

7.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

