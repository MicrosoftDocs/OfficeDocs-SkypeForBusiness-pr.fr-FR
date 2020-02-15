---
title: 'Lync Server 2013 : configuration de la stratégie globale pour la conversation permanente'
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
ms.openlocfilehash: 4131bca64c8faab6f1b616a02994fbccd9b435dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a>Configurer la stratégie globale pour la conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Vous pouvez utiliser la stratégie globale par défaut pour activer les paramètres de conversation permanente pour tous les utilisateurs de votre déploiement. Vous pouvez également spécifier des stratégies supplémentaires pour les sites et les utilisateurs afin de déterminer si la conversation permanente est activée ou désactivée pour des utilisateurs et des sites spécifiques.

Il est impossible de supprimer la stratégie globale. Si vous essayez de la supprimer, les valeurs par défaut de la configuration sont rétablies.

<div>


> [!NOTE]  
> Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Pour configurer les paramètres de configuration du serveur de conversation permanente, voir <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurer les options de serveur de conversation permanente globalement ou pour le pool de serveurs de conversation permanente dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Pour configurer la stratégie globale pour la conversation permanente

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md) dans la documentation des opérations.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, consultez la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de conversation permanente à l’aide des applets de commande Windows PowerShell</A> dans la documentation de déploiement.

    
    </div>

3.  Dans le panneau de configuration Lync Server, cliquez sur **conversation permanente**, puis sur **stratégie de conversation permanente**.

4.  Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut Globale.
    
      - Dans **Description**, fournissez des détails sur la stratégie de l’utilisateur (par exemple, stratégie globale pour centralSiteName).
    
      - Pour contrôler la conversation permanente pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **activer la conversation permanente** .

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

