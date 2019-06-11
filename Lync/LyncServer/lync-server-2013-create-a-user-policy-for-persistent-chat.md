---
title: 'Lync Server 2013 : Création d’une stratégie utilisateur pour la conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a1d2cd767af4cbee7c416dc8f600ed9e9e192a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a>Création d’une stratégie utilisateur pour la conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-06_

Le panneau de configuration de Lync Server vous permet de définir des stratégies utilisateur qui peuvent être affectées à des utilisateurs. ****

La stratégie utilisateur remplace les stratégies globales et de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie utilisateur est affectée.

<div>


> [!NOTE]  
> Pour configurer et utiliser le serveur de chat permanent, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de chat permanent à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajouter un serveur Chat permanent à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Pour configurer les paramètres de configuration de serveur Chat permanent, voir <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurer globalement les options de serveur de chat permanent ou pour le pool de serveurs de chat permanent dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a>Pour créer une stratégie utilisateur pour la discussion permanente

1.  À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration de Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des cmdlets Windows PowerShell. Pour plus d’informations, reportez-vous à la rubrique Configuration d’un <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">serveur de chat permanent en utilisant des applets de cmdlet Windows PowerShell</A> .

    
    </div>

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.

4.  Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.

5.  Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.
    
      - Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie de conversation permanente pour un utilisateur spécifique).
    
      - Pour contrôler la conversation permanente de tous les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie utilisateur, activez ou désactivez la case à cocher **activer les discussions permanentes** .

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

