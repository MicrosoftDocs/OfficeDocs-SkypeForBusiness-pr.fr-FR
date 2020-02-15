---
title: 'Lync Server 2013 : suppression des autorisations d’utilisateur authentifié'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd54da7201889e9ca2ab8d2c40a84ad082fa1686
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Les autorisations des utilisateurs authentifiés sont supprimées dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Dans un environnement Active Directory verrouillé, les entrées de contrôle d’accès (ACE) des utilisateurs authentifiés sont supprimées des conteneurs Active Directory par défaut, notamment Utilisateurs, Configuration ou Système, et des unités d’organisation (OU) où sont stockés les objets Utilisateur et Ordinateur. La suppression des entrées de contrôle d’accès des utilisateurs authentifiés empêche l’accès en lecture aux informations Active Directory. Toutefois, la suppression des ACE crée des problèmes pour Lync Server 2013, car cela dépend des autorisations en lecture sur ces conteneurs pour permettre aux utilisateurs d’exécuter la préparation du domaine.

Dans cette situation, l’appartenance au groupe Administrateurs du domaine, requise pour exécuter la préparation d’un domaine, l’activation du serveur et la création de pools, n’octroie plus l’accès en lecture aux informations Active Directory stockées dans les conteneurs par défaut. Vous devez octroyer manuellement les autorisations d’accès en lecture sur divers conteneurs du domaine racine de la forêt pour vérifier que la procédure préalable de préparation d’une forêt a abouti.

Pour permettre à un utilisateur d’exécuter la préparation d’un domaine, l’activation d’un serveur ou la création d’un pool dans un domaine autre que le domaine racine de la forêt, vous disposez des options suivantes :

  - Utilisez un compte membre du groupe administrateurs de l’entreprise pour exécuter la préparation du domaine.

  - Utilisez un compte qui est un membre du groupe Administrateurs du domaine et octroyez-lui des autorisations d’accès en lecture sur chacun des conteneurs suivants du domaine racine de la forêt :
    
      - Domaine
    
      - Configuration ou Système

Si vous ne voulez pas utiliser un compte qui est un membre du groupe Administrateurs d’entreprise pour exécuter la préparation d’un domaine ou d’autres tâches de configuration, octroyez explicitement l’accès en lecture au compte que vous voulez utiliser sur les conteneurs concernés de la racine de la forêt.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>Pour attribuer des autorisations d’accès en lecture sur les conteneurs dans le domaine racine de la forêt

1.  Ouvrez une session sur l’ordinateur lié au domaine racine de la forêt en utilisant un compte qui est un membre du groupe Administrateurs du domaine pour le domaine racine de la forêt.

2.  Exécutez adsiedit.msc pour le domaine racine de la forêt.
    
    Si les entrées de contrôle d’accès des utilisateurs authentifiés ont été supprimées du conteneur Domaine, Configuration ou Système, vous devez octroyer des autorisations en lecture seule au conteneur, en procédant comme indiqué ci-après.

3.  Cliquez avec le bouton droit sur le conteneur, puis cliquez sur **Propriétés**.

4.  Cliquez sur l’onglet **Sécurité**.

5.  Cliquez sur**Avancé**.

6.  Sous l'onglet**Autorisations**, cliquez sur**Ajouter**.

7.  Tapez le nom de l’utilisateur ou du groupe qui reçoit les autorisations en utilisant le `domain\account name`format suivant :, puis cliquez sur **OK**.

8.  Sous l’onglet **Objets**, dans **S’applique à**, cliquez sur **Cet objet uniquement**.

9.  Dans **Autorisations**, sélectionnez les entrées de contrôle d’accès suivantes en cliquant sur la colonne **Autoriser** : **Lister le contenu**, **Lire toutes les propriétés** et **Autorisations de lecture**.

10. Cliquez deux fois sur **OK**.

11. Répétez ces étapes pour tous les conteneurs concernés répertoriés à l’étape 2.

</div>

</div>

<span> </span>

</div>

</div>

</div>

