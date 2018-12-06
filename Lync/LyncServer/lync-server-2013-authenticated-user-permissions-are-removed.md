---
title: 'Lync Server 2013 : Suppression des autorisations d’utilisateur authentifié'
TOCTitle: Suppression des autorisations d’utilisateur authentifié
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398425(v=OCS.15)
ms:contentKeyID: 49297369
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression des autorisations d’utilisateur authentifié dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Dans un environnement Active Directory verrouillé, les entrées de contrôle d’accès (ACE) des utilisateurs authentifiés sont supprimées des conteneurs Active Directory par défaut, notamment Utilisateurs, Configuration ou Système, et des unités d’organisation (OU) où sont stockés les objets Utilisateur et Ordinateur. La suppression des entrées de contrôle d’accès des utilisateurs authentifiés empêche l’accès en lecture aux informations Active Directory. Cependant, la suppression des entrées de contrôle d’accès créé des problèmes pour Lync Server 2013, car celui-ci dépend de l’accès en lecture à ces conteneurs pour permettre aux utilisateurs d’exécuter la préparation d’un domaine.

Dans ce cas, l’appartenance au groupe Administrateurs du domaine, requise pour exécuter la préparation d’un domaine, l’activation du serveur et la création de pools, n’octroie plus l’accès en lecture aux informations Active Directory stockées dans les conteneurs par défaut. Vous devez octroyer manuellement les autorisations d’accès en lecture sur divers conteneurs du domaine racine de la forêt pour vérifier que la procédure préalable de préparation d’une forêt a abouti.

Pour permettre à un utilisateur d’exécuter la préparation d’un domaine, l’activation d’un serveur ou la création d’un pool dans un domaine autre que le domaine racine de la forêt, vous disposez des options suivantes :

  - Utilisez un compte qui est un membre du groupe Administrateurs d’entreprise pour exécuter la préparation d’un domaine.

  - Utilisez un compte qui est un membre du groupe Administrateurs du domaine et octroyez-lui des autorisations d’accès en lecture sur chacun des conteneurs suivants du domaine racine de la forêt :
    
      - Domaine
    
      - Configuration ou Système

Si vous ne voulez pas utiliser un compte qui est un membre du groupe Administrateurs d’entreprise pour exécuter la préparation d’un domaine ou d’autres tâches de configuration, octroyez explicitement l’accès en lecture au compte que vous voulez utiliser sur les conteneurs concernés de la racine de la forêt.

## Pour attribuer des autorisations d’accès en lecture sur les conteneurs dans le domaine racine de la forêt

1.  Ouvrez une session sur l’ordinateur lié au domaine racine de la forêt en utilisant un compte qui est un membre du groupe Administrateurs du domaine pour le domaine racine de la forêt.

2.  Exécutez adsiedit.msc pour le domaine racine de la forêt.
    
    Si les entrées de contrôle d’accès des utilisateurs authentifiés ont été supprimées du conteneur Domaine, Configuration ou Système, vous devez octroyer des autorisations en lecture seule au conteneur, en procédant comme indiqué ci-après.

3.  Cliquez avec le bouton droit sur le conteneur, puis cliquez sur **Propriétés** .

4.  Cliquez sur l’onglet **Sécurité** .

5.  Cliquez sur **Avancé** .

6.  Sous l’onglet **Autorisations** , cliquez sur **Ajouter** .

7.  Tapez le nom de l’utilisateur ou du groupe qui reçoit les autorisations en respectant le format suivant : `domain\account name`, puis cliquez sur **OK** .

8.  Sous l’onglet **Objets** , dans **S’applique à** , cliquez sur **Cet objet uniquement** .

9.  Dans **Autorisations** , sélectionnez les entrées de contrôle d’accès suivantes en cliquant sur la colonne **Autoriser**  : **Lister le contenu** , **Lire toutes les propriétés** et  **Autorisations de lecture** .

10. Cliquez deux fois sur **OK** .

11. Répétez ces étapes pour tous les conteneurs concernés répertoriés à l’étape 2.

