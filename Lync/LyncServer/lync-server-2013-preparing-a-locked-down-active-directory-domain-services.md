---
title: "Lync Server 2013 : Prép. des services de domaine Active Directory verrouillés"
TOCTitle: Préparation des services de domaine Active Directory verrouillés
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398492(v=OCS.15)
ms:contentKeyID: 49297484
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Préparation des services de domaine Active Directory verrouillés dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-05-14_

Les organisations verrouillent souvent services de domaine Active Directory pour réduire les risques de sécurité. Cependant, un environnement Active Directory verrouillé peut limiter les autorisations requises par Lync Server 2013. Pour préparer correctement un environnement Active Directory verrouillé pour Lync Server 2013, vous devez prendre en compte d’autres éléments et effectuer des étapes supplémentaires.

Deux méthodes courantes permettent de limiter les autorisations dans un environnement Active Directory verrouillé :

  - Les entrées de contrôle d’accès des utilisateurs authentifiés sont supprimées des conteneurs.

  - L’héritage des autorisations est désactivé dans les conteneurs des objets Utilisateur, Contact, InetOrgPerson ou Ordinateur.

## Dans cette section

  - [Suppression des autorisations d’utilisateur authentifié dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Désactivation de l’héritage des autorisations sur les conteneurs des objets Ordinateur, Utilisateur ou InetOrgPerson dans Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

