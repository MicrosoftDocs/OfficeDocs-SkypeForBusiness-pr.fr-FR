---
title: "Lync Server 2013 : Conf. prise en charge pour les domaines externes bloqués"
TOCTitle: Configuration de la prise en charge pour les domaines externes bloqués
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49297105
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la prise en charge pour les domaines externes bloqués dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-08_

Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez gérer les domaines qui n’auront pas accès à la fédération au sein de votre organisation. La liste des domaines bloqués sert de liste rouge (liste d’entrées explicites qui doivent être interdites) et s’applique à la découverte des domaines fédérés, si cette option est activée. Pour plus d’informations, reportez-vous à [Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Empêchez un ou plusieurs domaines externes de se connecter à votre organisation. Pour ce faire, ajoutez le domaine à la liste des domaines bloqués.

## Pour ajouter un domaine externe à la liste des domaines bloqués

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**.

4.  Cliquez sur **Domaines fédérés**, sur **Nouveau**, puis sur **Domaine bloqué**.

5.  Dans **Nouveaux domaines fédérés**, procédez comme suit :
    
      - Dans **Nom de domaine complet (ou FQDN)**, tapez le nom de domaine du partenaire fédéré que vous souhaitez bloquer.
        
        > [!NOTE]  
        > Il peut contenir jusqu’à 256 caractères.<br />
        La recherche du nom de domaine du partenaire fédéré établit une correspondance à partir du suffixe. Par exemple, si vous tapez <strong>contoso.com</strong> , la recherche renverra également le domaine <strong>it.contoso.com</strong>.<br />
        Un domaine de partenaire fédéré ne peut pas être simultanément bloqué et autorisé. Lync Server 2013 empêche cette situation afin que vous n’ayez pas à synchroniser vos listes.    
      - (Facultatif) Dans **Commentaire**, tapez les informations sur cette configuration que vous voulez partager avec les autres administrateurs système.

6.  Cliquez sur **Valider**.

7.  Répétez les étapes 4 à 6 pour chaque partenaire fédéré que vous souhaitez bloquer.

Pour activer l’accès des utilisateurs fédérés, vous devez aussi activer la prise en charge de l’accès des utilisateurs fédérés dans votre organisation. Pour plus d’informations, reportez-vous à [Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

En outre, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à collaborer avec les utilisateurs fédérés. Pour plus d’informations, reportez-vous à [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

