---
title: 'Lync Server 2013 : Suppression des autorisations d’utilisateur authentifié'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d5e14b8129f771093ed9facb09d047ac7c36d32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Suppression des autorisations d’utilisateur authentifié dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Dans un environnement Active Directory verrouillé, les entrées de contrôle d’accès des utilisateurs authentifiées (ACE) sont supprimées des conteneurs Active Directory par défaut, y compris des utilisateurs, de la configuration ou du système et des unités d’organisation (UO) sur lesquelles les utilisateurs et ordinateurs les objets sont stockés. La suppression des entrées ACE d’utilisateur authentifiés empêche l’accès en lecture aux informations Active Directory. Toutefois, la suppression des ACE génère des problèmes pour Lync Server 2013, car elle dépend des autorisations en lecture sur ces conteneurs pour permettre aux utilisateurs d’effectuer la préparation du domaine.

Dans ce cas, l’appartenance au groupe administrateurs de domaine, qui est nécessaire pour exécuter la préparation du domaine, l’activation du serveur et la création de pool, ne accorde plus l’accès en lecture aux informations Active Directory stockées dans les conteneurs par défaut. Pour vérifier la fin de la procédure de préparation de la forêt requise, vous devez attribuer manuellement des autorisations d’accès en lecture à divers conteneurs du domaine racine de la forêt.

Pour permettre à un utilisateur d’exécuter la préparation du domaine, l’activation du serveur ou la création de pool sur n’importe quel domaine racine sans forêt, vous disposez des options suivantes:

  - Utilisez un compte membre du groupe administrateurs d’entreprise pour exécuter la préparation du domaine.

  - Utilisez un compte membre du groupe administrateurs de domaine et octroyez des autorisations d’accès en lecture à ce compte sur chacun des conteneurs suivants dans le domaine racine de la forêt:
    
      - Domaines
    
      - Configuration ou système

Si vous ne voulez pas utiliser un compte membre du groupe administrateurs d’entreprise pour exécuter la préparation du domaine ou d’autres tâches de configuration, autorisez explicitement le compte auquel vous voulez utiliser l’accès en lecture sur les conteneurs pertinents de la racine de la forêt.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>Pour octroyer aux utilisateurs des autorisations de lecture dans le domaine racine de la forêt

1.  Ouvrez une session sur l’ordinateur joint au domaine racine de la forêt avec un compte membre du groupe administrateurs de domaine pour le domaine racine de la forêt.

2.  Exécutez adsied. msc pour le domaine racine de la forêt.
    
    Si les ACE d’utilisateur authentifiés ont été supprimées du domaine, de la configuration ou du conteneur système, vous devez accorder des autorisations en lecture seule au conteneur, comme décrit dans les étapes suivantes.

3.  Cliquez avec le bouton droit sur le conteneur, puis cliquez sur **Propriétés**.

4.  Cliquez sur l’onglet **sécurité** .

5.  Cliquez sur **Avancé**.

6.  Dans l’onglet **autorisations** , cliquez sur **Ajouter**.

7.  Entrez le nom du groupe ou de l’utilisateur en utilisant le format suivant: `domain\account name`, puis cliquez sur **OK**.

8.  Dans l’onglet **objets** , dans **s’applique à**, cliquez sur **cet objet uniquement**.

9.  Dans **autorisations**, sélectionnez les entrées ACE suivantes, puis cliquez sur l’option **autoriser** la colonne: **contenu**de la liste, **lecture de toutes les propriétés**et **autorisations de lecture**.

10. Cliquez sur **OK** à deux reprises.

11. Répétez ces étapes pour chacun des conteneurs pertinents répertoriés à l’étape 2.

</div>

</div>

<span> </span>

</div>

</div>

</div>

