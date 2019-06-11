---
title: 'Lync Server 2013 : Configuration des compléments pour les salles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb6525f67f22e09c4bf7ea40f575b3981e9a55c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Configuration des compléments pour les salles dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la section **complément** de la page de **conversation permanente** pour associer des URL à des salles de conversation permanentes. Ces URL apparaissent dans le client 2013 Lync dans la salle de conversation du volet extensibilité de la conversation. Un administrateur doit ajouter des compléments à la liste des compléments enregistrés, et les responsables de salles de conversation ou créateurs doivent associer des salles à un des compléments enregistrés avant que les utilisateurs puissent voir cette mise à niveau dans leur client Lync 2013.

Les compléments servent à étendre l’expérience dans la salle. Un complément classique peut inclure une URL pointant vers une application Silverlight qui intercepte quand un code d’action est publié dans une salle de conversation et affiche l’historique des actions dans le volet extensibilité. En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément servant à inclure un contexte partagé, comme « Tête de liste » ou « Sujet du jour ».

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>Configuration des compléments pour des salles de conversation

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration de Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des cmdlets Windows PowerShell. Pour plus d’informations, reportez-vous à <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de chat permanent à l’aide des cmdlets Windows PowerShell</A> dans la documentation de déploiement.

    
    </div>

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.
    
    Dans la liste déroulante des déploiements de pools de serveurs de chat permanent, sélectionnez le pool approprié.

4.  Dans la page **Complément**, cliquez sur **Créer**.

5.  Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de chat permanent pour lequel vous devez créer le complément. Les compléments ne peuvent pas être déplacés d’un pool vers un autre ou partagés entre les différents pools.

6.  Dans **Nouveau complément**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nom pour le nouveau complément.
    
      - Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Ouvrez les outils d’administration de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

