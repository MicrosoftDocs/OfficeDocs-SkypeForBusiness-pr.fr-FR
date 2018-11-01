---
title: "Lync Server 2013 : Conf. des stratégies de contrôle d’accès des ut. publics"
TOCTitle: Configuration des stratégies de contrôle d’accès des utilisateurs publics
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520946(v=OCS.15)
ms:contentKeyID: 49296181
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La connectivité PIC (Public IM Connectivity) permet aux utilisateurs de votre organisation d’utiliser la messagerie instantanée pour communiquer avec les utilisateurs des services de messagerie instantanée proposés par des fournisseurs de services de messagerie instantanée publics, notamment le réseau Windows Live de services Internet, Yahoo\! et AOL. Vous devez configurer un certain nombre de stratégies d’accès externe pour déterminer si des utilisateurs publics peuvent collaborer avec des utilisateurs de Lync Server internes. La connectivité PIC est une nouvelle fonctionnalité qui s’appuie sur la configuration de votre déploiement et les utilisateurs. Elle dépend également du provisionnement du service au niveau du fournisseur de messagerie instantané public. Pour plus d’informations sur le provisionnement de votre déploiement par des fournisseurs publics, consultez le guide « Guide de configuration de la connectivité PIC (Public IM Connectivity) pour Microsoft Lync Server, Office Communications Server et Live Communications Server » : <http://go.microsoft.com/fwlink/?linkid=269821>

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li></ul>


Pour accéder au site de provisionnement PIC (Public IM Connectivity) de Microsoft Lync Server, cliquez sur le lien suivant : <http://go.microsoft.com/fwlink/?linkid=212638>

Pour contrôler l’accès des utilisateurs publics, vous pouvez configurer des stratégies au niveau global, du site et des utilisateurs. Pour plus d’informations sur les types des stratégies que vous pouvez configurer, consultez [Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) dans la documentation de déploiement ou de planification. Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

Dans le cas des invitations de messagerie instantanée, la réponse dépend du logiciel client. La demande est acceptée, sauf si les expéditeurs externes sont explicitement bloqués par une règle configurée par l’utilisateur (c’est-à-dire les paramètres figurant dans les listes **Autoriser** et **Bloquer** ). De plus, les invitations de messagerie instantanée peuvent être bloquées si un utilisateur choisit de bloquer tous les messages instantanés des utilisateurs qui ne figurent pas dans sa liste **Autoriser**.

> [!NOTE]  
> Vous pouvez configurer des stratégies de contrôle d’accès des utilisateurs publics, même si vous n’avez pas activé la fédération pour votre organisation. Cependant, les stratégies que vous configurez s’appliquent uniquement si la fédération est activée pour votre organisation. Pour plus d’informations sur l’activation de la fédération, reportez-vous à <a href="lync-server-2013-enable-or-disable-remote-user-access.md">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</a> dans la documentation de déploiement ou des opérations. En outre, si vous spécifiez une stratégie de contrôle d’accès des utilisateurs publics, la stratégie s’applique uniquement aux utilisateurs activés pour Lync Server et configurés pour utiliser la stratégie. Pour plus d’informations sur la désignation d’utilisateurs publics pouvant se connecter à Lync Server, consultez <a href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013</a> dans la documentation de déploiement ou des opérations.

Effectuez la procédure suivante pour configurer une stratégie permettant de prendre en charge l’accès par les utilisateurs d’un ou plusieurs fournisseurs de messagerie instantanée publics.

## Pour configurer une stratégie d’accès externe pour la prise en charge de l’accès des utilisateurs publics

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale permettant la prise en charge de l’accès des utilisateurs publics, cliquez sur **Modifier**, puis sur **Afficher les détails**.
    
      - Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie d’accès externe**, créez dans le champ **Nom** un nom unique qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie utilisateur qui autorise les communications des utilisateurs publics).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des actions suivantes :
    
      - Pour activer l’accès des utilisateurs publics pour la stratégie, activez la case à cocher **Autoriser les communications avec des utilisateurs publics**.
    
      - Pour désactiver l’accès des utilisateurs publics pour la stratégie, désactivez la case à cocher **Autoriser les communications avec des utilisateurs publics**.

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs publics, vous devez aussi activer la prise en charge de la fédération dans votre organisation. Pour plus d’informations, reportez-vous à [Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

S’il s’agit d’une stratégie utilisateur, vous devez aussi appliquer la stratégie aux utilisateurs publics que vous souhaitez autoriser à collaborer avec les utilisateurs publics. Pour plus d’informations, reportez-vous à [Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

## Voir aussi

#### Tâches

[Création ou modification des fournisseurs fédérés SIP publics dans Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  

#### Autres ressources

[Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

