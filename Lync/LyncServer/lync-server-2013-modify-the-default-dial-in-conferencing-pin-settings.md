---
title: "Lync Server 2013 : Mod. des par. de code conf. des conférences rdv par déf."
TOCTitle: Modification des paramètres de code confidentiel des conférences rendez-vous par défaut
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425780(v=OCS.15)
ms:contentKeyID: 49296727
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification des paramètres de code confidentiel des conférences rendez-vous par défaut dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-18_

La stratégie d’authentification par code confidentiel globale définit les règles des codes confidentiels pour les conférences rendez-vous au niveau forêt. Pour modifier cette stratégie, procédez comme suit. Pour plus d’informations sur la création ou la modification d’une stratégie de code confidentiel de conférence rendez-vous au niveau site ou utilisateur, reportez-vous à [Création ou modification des paramètres de code confidentiel dans Lync Server 2013 pour les conférences rendez-vous pour un site ou un groupe d’utilisateurs](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).

## Pour modifier la stratégie de code confidentiel globale

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de code confidentiel**.

4.  Dans la page **Stratégie de code confidentiel**, cliquez sur la stratégie **Globale**, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie de code confidentiel**, dans **Longueur minimale du code confidentiel**, tapez ou sélectionnez la longueur minimale du code confidentiel que vous voulez autoriser. La longueur minimale par défaut est de cinq chiffres.

6.  Si vous voulez spécifier le nombre maximal de tentatives de connexion avant le verrouillage de l’utilisateur, activez la case à cocher **Spécifier le nombre maximal de tentatives de connexion**. Si vous ne sélectionnez pas cette option, le nombre maximal de tentatives est automatiquement déterminé en fonction de la longueur du code confidentiel. Par défaut, le nombre maximal de tentatives est automatiquement déterminé.

7.  Si vous avez activé la case à cocher **Spécifier le nombre maximal de tentatives de connexion**, dans **Nombre maximal de tentatives de connexion**, tapez ou sélectionnez le nombre maximal de tentatives de connexion que vous souhaitez autoriser.

8.  Si vous voulez que les codes confidentiels expirent, activez la case à cocher **Activer l’expiration du code confidentiel**. Si vous ne sélectionnez pas cette option, les codes confidentiels n’expirent jamais. Par défaut, les codes confidentiels n’expirent jamais.

9.  Si vous avez activé la case à cocher **Activer l’expiration du code confidentiel**, dans **Le code confidentiel expire au bout de (jours)**, tapez ou sélectionnez le nombre de jours après lequel les codes confidentiels expirent.

10. Dans **Comptage de l’historique du code confidentiel**, tapez le nombre de codes confidentiels qu’un utilisateur doit créer avant qu’il ne puisse réutiliser un code. Par défaut, les utilisateurs peuvent réutiliser leur code confidentiel.

11. Pour autoriser les modèles courants de codes confidentiels, tels que les jeux de chiffres séquentiels et répétitifs, activez la case à cocher **Autoriser les modèles courants**. Si vous ne sélectionnez pas cette option, seuls les modèles complexes de chiffres sont autorisés. Par défaut, seuls les modèles complexes de chiffres sont autorisés.
    
    > [!IMPORTANT]  
    > Nous vous recommandons de ne pas autoriser les modèles courants.

12. Cliquez sur **Valider**.

