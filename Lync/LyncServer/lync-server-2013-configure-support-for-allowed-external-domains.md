---
title: "Lync Server 2013 : Conf. de la prise en ch. des domaines externes autorisés"
TOCTitle: Configuration de la prise en charge des domaines externes autorisés
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425908(v=OCS.15)
ms:contentKeyID: 49296990
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la prise en charge des domaines externes autorisés dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez décider des domaines qui sont autorisés à se fédérer avec votre organisation. Vous devez configurer un ou plusieurs domaines externes spécifiques en tant que domaines fédérés autorisés. Pour ce faire, ajoutez chaque domaine à la liste des domaines autorisés. Même si la découverte de partenaire est activée pour votre organisation, effectuez cette opération si le domaine est un partenaire fédéré qui devra peut-être communiquer avec plus de 1 000 de vos utilisateurs ou envoyer plus de 20 messages par seconde. Si la découverte de partenaire est désactivée pour votre organisation, seuls les utilisateurs des domaines externes que vous ajoutez à la liste des domaines autorisés peuvent utiliser la messagerie instantanée et les services de conférence avec les utilisateurs de votre organisation. Si vous souhaitez limiter l’accès d’un domaine fédéré à un serveur spécifique qui exécute le service Edge d’accès du partenaire fédéré, vous pouvez spécifier le nom de domaine du serveur exécutant le service Edge d’accès pour chaque domaine présent dans la liste des domaines autorisés.

> [!NOTE]  
> Cette procédure décrit la façon de configurer la prise en charge de domaines spécifiques, mais l’implémentation de la prise en charge des utilisateurs fédérés nécessite également d’activer la prise en charge des utilisateurs fédérés pour votre organisation, mais aussi de configurer et d’appliquer des stratégies permettant de spécifier les utilisateurs qui sont autorisés à collaborer avec les utilisateurs fédérés. Pour plus d’informations sur l’activation de la prise en charge des utilisateurs fédérés, reportez-vous à <a href="lync-server-2013-enable-or-disable-remote-user-access.md">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</a>. Pour plus d’informations sur la configuration des stratégies permettant de contrôler la fédération, reportez-vous à <a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</a>.

## Pour ajouter un domaine externe à la liste des domaines autorisés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes** , puis cliquez sur **Domaines fédérés** .

4.  Dans la page **Domaines fédérés** , cliquez sur **Nouveau** , puis sur **Domaine autorisé** .

5.  Dans **Nouveaux domaines fédérés** , procédez comme suit :
    
      - Dans **Nom de domaine complet (ou FQDN)** , tapez le nom de domaine du partenaire fédéré.
        
        > [!NOTE]  
        > Ce nom doit être unique et ne doit pas déjà exister en tant que domaine autorisé pour ce serveur exécutant le service Edge d’accès. Il peut contenir jusqu’à 256 caractères.<br />
        La recherche du nom de domaine du partenaire fédéré établit une correspondance à partir du suffixe. Par exemple, si vous tapez <strong>contoso.com</strong> , la recherche renverra également le domaine <strong>it.contoso.com</strong> .<br />
        Un domaine de partenaire fédéré ne peut pas être simultanément bloqué et autorisé. Lync Server 2013 empêche cette situation afin que vous n’ayez pas à synchroniser vos listes.    
      - Si vous souhaitez restreindre l’accès pour ce domaine fédéré aux utilisateurs d’un serveur spécifique qui exécute le service Edge d’accès, dans **Service Edge d’accès (FQDN)** , tapez le nom de domaine complet du serveur de domaine fédéré exécutant le service Edge d’accès.
    
      - Si vous souhaitez fournir des informations supplémentaires, dans **Commentaire** , tapez les informations sur cette configuration que vous voulez partager avec les autres administrateurs système.

6.  Cliquez sur **Valider** .

7.  Répétez les étapes 4 à 6 pour chaque domaine de partenaire fédéré que vous souhaitez autoriser.

Pour activer l’accès des utilisateurs fédérés, vous devez aussi activer la prise en charge de l’accès des utilisateurs fédérés dans votre organisation. Pour plus d’informations, reportez-vous à [Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

En outre, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à collaborer avec les utilisateurs fédérés. Pour plus d’informations, reportez-vous à [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

