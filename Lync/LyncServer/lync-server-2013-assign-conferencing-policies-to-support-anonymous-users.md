---
title: "LS 2013 : Affect. des strat. de conf. pour la prise en ch. les ut. anonymes"
TOCTitle: Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521007(v=OCS.15)
ms:contentKeyID: 49297447
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

Par défaut, aucun utilisateur ne peut inviter d’utilisateurs anonymes à participer à une réunion. Pour déterminer quels sont les utilisateurs qui peuvent inviter des utilisateurs anonymes, vous devez configurer une stratégie de conférence pour la prise en charge des utilisateurs anonymes, et appliquer cette stratégie de conférence à des utilisateurs spécifiques. Pour plus d’informations sur la configuration des stratégies de conférence pour la prise en charge des utilisateurs anonymes, reportez-vous à [Création ou modification d’une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) et [Gestion de la fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Suivez la procédure décrite dans cette section pour appliquer une stratégie de conférence, que vous avez déjà créée, à un ou plusieurs utilisateurs ou groupes d’utilisateurs.

> [!NOTE]  
> Outre la configuration et l’application d’une stratégie pour permettre aux utilisateurs d’inviter des utilisateurs anonymes, vous devez aussi activer la prise en charge des utilisateurs anonymes pour votre organisation. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013</a>.

## Pour configurer une stratégie utilisateur en vue d’une participation anonyme aux réunions

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis effectuez l’une des opérations suivantes :
    
    1.  Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans le champ **Nom**, créez un nom unique indiquant ce qu’englobe la stratégie utilisateur (par exemple, **AutoriserAnonyme** pour une stratégie utilisateur qui autorise les communications avec des utilisateurs anonymes).
    
    2.  Pour configurer une stratégie utilisateur existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

4.  Dans la boîte de dialogue **Stratégies de conférence**, activez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes**.

5.  Cliquez sur **Valider**.

6.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

7.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

8.  Dans **Modifier l’utilisateur Lync Server**, sous **Stratégie de conférence**, sélectionnez la stratégie utilisateur spécifiant la configuration d’accès utilisateur anonyme que vous souhaitez appliquer à cet utilisateur.
    
    > [!NOTE]  
    > Les paramètres <strong>&lt;Automatique&gt;</strong> mettent en œuvre les paramètres d’installation du serveur par défaut et sont appliqués automatiquement par le serveur.

Pour autoriser les utilisateurs à inviter des utilisateurs anonymes à des conférences, vous devez aussi activer la prise en charge des utilisateurs anonymes dans votre organisation. Pour plus d’informations, reportez-vous à [Configuration des stratégies de contrôle d’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) dans la documentation de déploiement ou des opérations.

