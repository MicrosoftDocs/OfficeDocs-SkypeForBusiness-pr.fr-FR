---
title: 'Lync Server 2013 : configuration des compléments pour les salles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40a9e7a2c947d18e8359e2199ec8c3e40e00ed98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Configurer des compléments pour les salles dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la section **complément** de la page **conversation permanente** pour associer des URL à des salles de conversation permanentes. Ces URL apparaissent dans le client Lync 2013 dans la salle de conversation dans le volet d’extensibilité de conversation. Un administrateur doit ajouter des compléments à la liste des compléments inscrits, et les gestionnaires de salle de conversation/créateurs doivent associer des salles à l’un des compléments inscrits pour que les utilisateurs puissent voir cette mise à niveau dans leur client Lync 2013.

Les compléments servent à étendre l’expérience dans la salle. Un complément classique peut inclure une URL pointant vers une application Silverlight qui intercepte quand un ticker boursier est publié dans une salle de conversation et affiche l’historique des actions dans le volet d’extensibilité. En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément pour inclure un contexte partagé, tel que « Tête de liste » ou « Sujet du jour ».

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>Pour configurer des compléments pour des salles de conversation

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent Chat Server by Using Windows PowerShell Cmdlets</A> dans la documentation de déploiement.

    
    </div>

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.
    
    Pour plusieurs déploiements de pool de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.

4.  Dans la page **Complément**, cliquez sur **Nouveau**.

5.  Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente dans lequel vous devez créer le complément. Les compléments ne peuvent pas être déplacés d’un pool à un autre ou partagés parmi différents pools.

6.  Dans **Nouveau complément**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nom pour le nouveau complément.
    
      - Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Ouvrir les outils d’administration de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Configuration du serveur de conversation permanente à l’aide des applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

