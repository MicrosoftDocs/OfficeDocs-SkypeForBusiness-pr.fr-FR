---
title: "Lync Server 2013 : Cond. prér. à l’activation de l’authentification Kerberos"
TOCTitle: Conditions prérequises à l’activation de l’authentification Kerberos
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425909(v=OCS.15)
ms:contentKeyID: 49296988
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conditions prérequises à l’activation de l’authentification Kerberos dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Avant d’activer l’authentification Kerberos, veillez à préparer toutes les configurations et infrastructures prérequises :

  - Le schéma Active Directory est étendu pour Lync Server 2013.

  - La préparation de la forêt Active Directory a été effectuée pour Lync Server 2013.

  - La préparation du domaine Active Directory a été effectuée pour Lync Server 2013.

  - magasin central de gestion est installé et disponible.

  - La topologie a été créée et publiée à l’aide de Générateur de topologie.

  - Les serveurs et les rôles qui requièrent services web ont été définis et déployés, dont les serveurs frontaux, les serveurs Standard Edition et les directeurs.

  - Les services Internet (IIS) sont configurés et déployés avec les services de rôle recommandés pour la prise en charge des services web dans Lync Server 2013.

Une fois que vous avez vérifié que les conditions préalables sont respectées, vous pouvez créer un ou plusieurs comptes pour les services web qui permettront l’authentification Kerberos dans le cadre de votre déploiement. Vous devez créer au moins un compte d’authentification Kerberos pour chaque déploiement. Néanmoins, vous pouvez créer un compte pour chaque site afin de permettre l’authentification Kerberos locale au niveau du site. Vous ne pouvez spécifier qu’un seul compte d’authentification Kerberos par site.

