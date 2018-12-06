---
title: "Lync Server 2013 : Act. d’une stratégie de serveur de conversation permanente"
TOCTitle: Activation d’une stratégie de serveur de conversation permanente
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205056(v=OCS.15)
ms:contentKeyID: 49297973
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation d’une stratégie de serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Dans le Panneau de configuration Lync Server 2013, vous pouvez utiliser la page **Stratégie de conversation permanente** du groupe **conversation permanente** pour gérer les stratégies au niveau utilisateur, site, pool ou global, y compris configurer la stratégie globale par défaut et créer une ou plusieurs autres stratégies utilisateur et de site pour votre déploiement. Si un utilisateur est activé pour serveur de conversations permanentes par stratégie, l’environnement de serveur de conversations permanentes s’affiche son son client Lync 2013.

> [!NOTE]  
> Dans la topologie, les stratégies de sites de serveur de conversations permanentes s’appliquent globalement, par pool d’utilisateur, par site d’utilisateur ou par utilisateur.

La stratégie globale est créée automatiquement lorsque vous déployez le serveur de conversations permanentes et elle peut être configurée, mais pas supprimée. La stratégie globale s’appliquant à tous les utilisateurs, il n’est pas obligatoire de la définir par utilisateur.

Vous pouvez créer et configurer plusieurs stratégies utilisateur et de site qui, avec la stratégie globale, activent les utilisateurs pour le serveur de conversations permanentes. Les stratégies de serveur de conversations permanentes de pool et de site supplantent la stratégie globale de serveur de conversations permanentes, mais uniquement pour les utilisateurs de ce site. Les stratégies utilisateur supplantent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est affectée.

> [!NOTE]  
> Pour configurer et utiliser le serveur de conversations permanentes, vous devez d’abord utiliser le Générateur de topologie pour ajouter la prise en charge du serveur de conversations permanentes à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement.

## Dans cette section

  - [Configuration de la stratégie globale pour la conversation permanente dans Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Création d’une stratégie de site pour la conversation permanente dans Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Création d’une stratégie utilisateur pour la conversation permanente dans Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Application d’une stratégie de conversation permanente à un utilisateur ou à un groupe d’utilisateurs dans Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

