---
title: 'Lync Server 2013 : Configuration de la stratégie globale pour la conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49fb5f329851436e503a9e3e42e144353b70017f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Configuration de la stratégie globale pour la conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Vous pouvez utiliser la stratégie globale par défaut pour activer les paramètres de conversation permanente de tous les utilisateurs de votre déploiement. Vous pouvez également spécifier des stratégies supplémentaires pour les sites et les utilisateurs pour contrôler si la conversation permanente est activée ou désactivée pour des utilisateurs et des sites spécifiques.

Vous ne pouvez pas supprimer la politique globale. Si vous essayez de la supprimer, la configuration réinitialise les valeurs par défaut.

<div>


> [!NOTE]  
> Pour configurer et utiliser le serveur de chat permanent, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de chat permanent à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajouter un serveur Chat permanent à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Pour configurer les paramètres de configuration de serveur Chat permanent, voir <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurer globalement les options de serveur de chat permanent ou pour le pool de serveurs de chat permanent dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Pour configurer la stratégie globale pour la conversation permanente

1.  À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration de Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) dans la documentation sur les opérations.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des cmdlets Windows PowerShell. Pour plus d’informations, reportez-vous à <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de chat permanent à l’aide des applets de cmdlet Windows PowerShell</A> dans la documentation de déploiement.

    
    </div>

3.  Dans le panneau de configuration de Lync Server, cliquez sur **conversation permanente**, puis cliquez sur **stratégie de conversation persistante**.

4.  Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».
    
      - Dans **Description**, indiquez les détails relatifs à la stratégie de l’utilisateur (par exemple, la stratégie globale pour centralSiteName).
    
      - Pour contrôler les discussions permanentes pour tous les sites et les utilisateurs qui ne sont pas spécifiquement contrôlés par le biais d’une stratégie de site ou d’un utilisateur, cochez ou décochez la case **activer les discussions permanentes** .

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

