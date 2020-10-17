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
ms.openlocfilehash: 8cf9f63fbe5340b3a241fc60b8623f54906dd8cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515761"
---
# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="77dfb-102">Les autorisations des utilisateurs authentifiés sont supprimées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77dfb-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77dfb-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="77dfb-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="77dfb-104">Dans un environnement Active Directory verrouillé, les entrées de contrôle d’accès (ACE) des utilisateurs authentifiés sont supprimées des conteneurs Active Directory par défaut, notamment Utilisateurs, Configuration ou Système, et des unités d’organisation (OU) où sont stockés les objets Utilisateur et Ordinateur.</span><span class="sxs-lookup"><span data-stu-id="77dfb-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="77dfb-105">La suppression des entrées de contrôle d’accès des utilisateurs authentifiés empêche l’accès en lecture aux informations Active Directory.</span><span class="sxs-lookup"><span data-stu-id="77dfb-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="77dfb-106">Toutefois, la suppression des ACE crée des problèmes pour Lync Server 2013, car cela dépend des autorisations en lecture sur ces conteneurs pour permettre aux utilisateurs d’exécuter la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="77dfb-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="77dfb-p102">Dans cette situation, l’appartenance au groupe Administrateurs du domaine, requise pour exécuter la préparation d’un domaine, l’activation du serveur et la création de pools, n’octroie plus l’accès en lecture aux informations Active Directory stockées dans les conteneurs par défaut. Vous devez octroyer manuellement les autorisations d’accès en lecture sur divers conteneurs du domaine racine de la forêt pour vérifier que la procédure préalable de préparation d’une forêt a abouti.</span><span class="sxs-lookup"><span data-stu-id="77dfb-p102">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers. You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="77dfb-109">Pour permettre à un utilisateur d’exécuter la préparation d’un domaine, l’activation d’un serveur ou la création d’un pool dans un domaine autre que le domaine racine de la forêt, vous disposez des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="77dfb-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="77dfb-110">Utilisez un compte membre du groupe administrateurs de l’entreprise pour exécuter la préparation du domaine.</span><span class="sxs-lookup"><span data-stu-id="77dfb-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="77dfb-111">Utilisez un compte qui est un membre du groupe Administrateurs du domaine et octroyez-lui des autorisations d’accès en lecture sur chacun des conteneurs suivants du domaine racine de la forêt :</span><span class="sxs-lookup"><span data-stu-id="77dfb-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="77dfb-112">Domaine</span><span class="sxs-lookup"><span data-stu-id="77dfb-112">Domain</span></span>
    
      - <span data-ttu-id="77dfb-113">Configuration ou Système</span><span class="sxs-lookup"><span data-stu-id="77dfb-113">Configuration or System</span></span>

<span data-ttu-id="77dfb-114">Si vous ne voulez pas utiliser un compte qui est un membre du groupe Administrateurs d’entreprise pour exécuter la préparation d’un domaine ou d’autres tâches de configuration, octroyez explicitement l’accès en lecture au compte que vous voulez utiliser sur les conteneurs concernés de la racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="77dfb-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="77dfb-115">Pour attribuer des autorisations d’accès en lecture sur les conteneurs dans le domaine racine de la forêt</span><span class="sxs-lookup"><span data-stu-id="77dfb-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="77dfb-116">Ouvrez une session sur l’ordinateur lié au domaine racine de la forêt en utilisant un compte qui est un membre du groupe Administrateurs du domaine pour le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="77dfb-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="77dfb-117">Exécutez adsiedit.msc pour le domaine racine de la forêt.</span><span class="sxs-lookup"><span data-stu-id="77dfb-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="77dfb-118">Si les entrées de contrôle d’accès des utilisateurs authentifiés ont été supprimées du conteneur Domaine, Configuration ou Système, vous devez octroyer des autorisations en lecture seule au conteneur, en procédant comme indiqué ci-après.</span><span class="sxs-lookup"><span data-stu-id="77dfb-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="77dfb-119">Cliquez avec le bouton droit sur le conteneur, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="77dfb-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="77dfb-120">Cliquez sur l’onglet **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="77dfb-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="77dfb-121">Cliquez sur**Avancé**.</span><span class="sxs-lookup"><span data-stu-id="77dfb-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="77dfb-122">Sous l'onglet**Autorisations**, cliquez sur**Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="77dfb-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="77dfb-123">Tapez le nom de l’utilisateur ou du groupe qui reçoit les autorisations en utilisant le format suivant : `domain\account name` , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="77dfb-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="77dfb-124">Sous l’onglet **Objets**, dans **S’applique à**, cliquez sur **Cet objet uniquement**.</span><span class="sxs-lookup"><span data-stu-id="77dfb-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="77dfb-125">Dans **Autorisations**, sélectionnez les entrées de contrôle d’accès suivantes en cliquant sur la colonne **Autoriser** : **Lister le contenu**, **Lire toutes les propriétés** et **Autorisations de lecture**.</span><span class="sxs-lookup"><span data-stu-id="77dfb-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="77dfb-126">Cliquez deux fois sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="77dfb-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="77dfb-127">Répétez ces étapes pour tous les conteneurs concernés répertoriés à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="77dfb-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

