---
title: "LS 2013 : Créa., mod. par. de code confi. des conf. rdv pr site ou gr. ut."
TOCTitle: Création ou modification des paramètres de code confidentiel des conférences rendez-vous pour un site ou un groupe d’utilisateurs
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412959(v=OCS.15)
ms:contentKeyID: 49298739
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification des paramètres de code confidentiel dans Lync Server 2013 pour les conférences rendez-vous pour un site ou un groupe d’utilisateurs

 

_**Dernière rubrique modifiée :** 2012-10-18_

Procédez comme suit pour créer ou modifier une stratégie de code confidentiel de conférence rendez-vous au niveau de l’utilisateur ou du site. Pour en savoir plus sur la manière de modifier la stratégie de code confidentiel globale, reportez-vous à [Modification des paramètres de code confidentiel des conférences rendez-vous par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).

## Pour créer une stratégie de code confidentiel au niveau utilisateur ou site

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.

4.  Dans la page **Stratégie de code confidentiel**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie au niveau utilisateur, cliquez sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie de code confidentiel**, dans **Nom**, tapez un nom décrivant la stratégie.
    
      - Pour créer une stratégie au niveau site, cliquez sur **Stratégie du site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites, cliquez sur le site voulu, puis sur **OK**.

5.  Dans le champ **Description**, tapez la description de la stratégie de code confidentiel.

6.  Dans le champ **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous souhaitez autoriser. La longueur minimale par défaut est de cinq chiffres.

7.  Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est automatiquement déterminé en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est automatiquement déterminé.

8.  Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion que vous souhaitez autoriser.

9.  Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.

10. Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.

11. Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant qu’il ne puisse réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.

12. Pour autoriser les modèles courants de codes confidentiels, tels que les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.
    
    > [!IMPORTANT]  
    > Nous vous recommandons de ne pas autoriser les modèles courants.

13. Cliquez sur **Valider**.

## Pour modifier une stratégie de code confidentiel au niveau de l’utilisateur ou du site

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.

4.  Dans la page **Stratégie de code confidentiel**, cliquez successivement sur la stratégie de code confidentiel à modifier, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie de code confidentiel**, modifiez tous les paramètres de la stratégie (à l’exception de son nom qui ne peut être modifié).

6.  Cliquez sur **Valider**.

