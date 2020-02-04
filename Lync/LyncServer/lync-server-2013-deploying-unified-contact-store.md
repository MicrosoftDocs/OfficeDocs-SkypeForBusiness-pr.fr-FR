---
title: 'Lync Server 2013 : Déploiement d’un magasin de contacts unifié'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d224ec7a9c452c45f9f3471403301460a2a31cc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="b8b2b-102">Déploiement d’un magasin de contacts unifié dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8b2b-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8b2b-103">_**Dernière modification de la rubrique :** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="b8b2b-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="b8b2b-104">L’activation d’un magasin de contacts unifié dans Lync Server 2013 ne nécessite aucun paramètre de topologie.</span><span class="sxs-lookup"><span data-stu-id="b8b2b-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="b8b2b-105">L’activation du magasin de contacts unifié pour les utilisateurs nécessite ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b8b2b-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="b8b2b-106">La stratégie du magasin de contacts unifié est activée (par défaut).</span><span class="sxs-lookup"><span data-stu-id="b8b2b-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="b8b2b-107">Les utilisateurs se connectent avec Lync 2013 au moins une fois.</span><span class="sxs-lookup"><span data-stu-id="b8b2b-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="b8b2b-108">Après la migration des contacts d’un utilisateur, ce qui se produit automatiquement lorsqu’un utilisateur se connecte à l’aide de Lync 2013, l’utilisateur peut accéder et gérer ses contacts Lync à partir de Lync 2013, Outlook 2013 ou Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="b8b2b-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="b8b2b-109">L’utilisateur n’a pas besoin d’être connecté à Lync pour gérer ses contacts à partir d’Outlook ou d’Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="b8b2b-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b8b2b-110">Si un utilisateur se connecte à partir de Lync 2010 après la migration, les contacts et les groupes sont disponibles et à jour, mais l’utilisateur ne peut pas gérer (c’est-à-dire ajouter, supprimer, déplacer, marquer, supprimer ou modifier) ces contacts.</span><span class="sxs-lookup"><span data-stu-id="b8b2b-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b8b2b-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b8b2b-111">In This Section</span></span>

  - [<span data-ttu-id="b8b2b-112">Activation des utilisateurs pour le magasin de contacts unifié dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8b2b-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="b8b2b-113">Migration des utilisateurs vers le magasin de contacts unifié dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8b2b-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="b8b2b-114">Restauration des utilisateurs migrés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b8b2b-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

