---
title: 'Lync Server 2013 : Annexe B : Gestion d’un Survivable Branch Appliance'
TOCTitle: 'Annexe B : Gestion d’un Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425797(v=OCS.15)
ms:contentKeyID: 49296750
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Annexe B : Gestion d’un Survivable Branch Appliance dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-18_

Cette rubrique décrit les procédures de gestion d’un Survivable Branch Appliance. En particulier, comment remplacer et renommer un Survivable Branch Appliance et comment changer le pool de serveurs frontaux Lync Server 2013 auquel le Survivable Branch Appliance est associé.

## Pour remplacer un Survivable Branch Appliance

1.  Arrêtez tous les services Lync Server 2013 sur le Survivable Branch Appliance. (Reportez-vous à la documentation du fournisseur du Survivable Branch Appliance.)

2.  (Recommandé) Supprimez le Survivable Branch Appliance du domaine.

3.  Supprimez l’objet ordinateur Survivable Branch Appliance dans les services de domaine Active Directory, en procédant comme suit :
    
      - Ouvrez une session sur un serveur membre, en tant que membre du groupe Administrateurs d’entreprise.
    
      - Cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **Utilisateurs et ordinateurs Active Directory** .
    
      - Cliquez avec le bouton droit sur l’objet Survivable Branch Appliance, puis cliquez sur **Supprimer** .

4.  Ajoutez de nouveau l’objet ordinateur Survivable Branch Appliance. (Reportez-vous à [Ajout d’un Survivable Branch Appliance à Active Directory dans Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)

5.  Patientez le temps que la réplication Active Directory se termine.

6.  Ouvrez Lync Server Management Shell, puis tapez **Enable-CSTopology** .

7.  Connectez le nouveau Survivable Branch Appliance au réseau, puis procédez comme indiqué dans les sections [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013 - Tâches pour un site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server sur un site de succursale avec Lync Server 2013 - tâche de site de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

## Pour renommer un Survivable Branch Appliance

1.  Déplacez les utilisateurs vers le site central. Pour plus d’informations, reportez-vous à [Déplacer les utilisateurs vers un autre outil dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrêtez tous les services Lync Server 2013 sur le Survivable Branch Appliance. (Reportez-vous à la documentation du fournisseur du Survivable Branch Appliance.)

3.  Supprimez le Survivable Branch Appliance de la topologie, en procédant comme suit :
    
      - Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Microsoft Lync Server** , puis sur **Générateur de topologie Lync Server** .
    
      - Dans l’arborescence de la console, développez **Sites de succursale** , cliquez sur Survivable Branch Appliance, puis sur **Supprimer** dans le volet Actions.

4.  Supprimez le Survivable Branch Appliance du domaine.

5.  Supprimez l’objet ordinateur Survivable Branch Appliance dans les Active Directory, en procédant comme suit :
    
      - Ouvrez une session sur un contrôleur de domaine en tant que membre du groupe Administrateurs d’entreprise.
    
      - Cliquez sur **Démarrer** , sur **Outils d’administration** , puis sur **Utilisateurs et ordinateurs Active Directory** .
    
      - Cliquez avec le bouton droit sur l’objet Survivable Branch Appliance, puis cliquez sur **Supprimer** .

6.  Restaurez les paramètres d’usine du Survivable Branch Appliance. (Reportez-vous à la documentation du fournisseur du Survivable Branch Appliance.)

7.  Procédez comme indiqué dans les sections [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013 - Tâches pour un site central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) et [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server sur un site de succursale avec Lync Server 2013 - tâche de site de succursale](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).

8.  Déplacez les utilisateurs vers le Survivable Branch Appliance renommé. Pour plus d’informations, reportez-vous à [Déplacer les utilisateurs vers un autre outil dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

## Pour changer le pool de serveurs frontaux Lync Server auquel le Survivable Branch Appliance est associé

1.  Déplacez les utilisateurs du Survivable Branch Appliance vers le pool de serveurs frontaux Lync Server du site central. Pour plus d’informations, reportez-vous à [Déplacer les utilisateurs vers un autre outil dans Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).

2.  Arrêtez tous les services Lync Server sur le Survivable Branch Appliance. (Reportez-vous à la documentation du fournisseur du Survivable Branch Appliance.)

3.  Mettez à jour le pool de serveurs frontaux Lync Server auquel le Survivable Branch Appliance est associé, en procédant comme suit :
    
      - Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Microsoft Lync Server** , puis sur **Générateur de topologie Lync Server** .
    
      - Développez **Sites de succursale** .
    
      - Cliquez avec le bouton droit sur l’objet Survivable Branch Appliance à modifier et cliquez sur **Modifier les propriétés**
    
      - Sous Résistance, sélectionnez le nouveau pool de serveurs frontaux auquel le Survivable Branch Appliance doit être associé, puis cliquez sur **Suivant** .
    
      - Dans l’arborescence de la console, cliquez avec le bouton droit sur le nouveau Survivable Branch Appliance, cliquez sur **Topologie** , puis sur **Publier** .

4.  Redémarrez tous les services Lync Server sur le Survivable Branch Appliance.

5.  Testez le Survivable Branch Appliance. Pour plus d’informations, reportez-vous à [Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).

6.  Déplacez les utilisateurs du pool frontal Lync Server du site central vers le Survivable Branch Appliance.

