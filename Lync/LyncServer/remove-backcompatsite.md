---
title: Supprimer BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6a3d1dc92e45bc99892e7827394376b6f28b12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>Supprimer BackCompatSite

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Une fois que tous les pools ont été désactivés et que tous les serveurs Edge ont été désinstallés, exécutez l’Assistant Fusion du générateur de topologie pour supprimer **BackCompatSite**.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>Pour supprimer le site de recompatibilité dans le générateur de topologie

1.  Ouvrez un déploiement existant à partir du générateur de topologie.

2.  Dans le menu **action** , cliquez sur fusionner la **topologie 2007 R2**.

3.  Cliquez sur **Suivant** pour continuer.

4.  Dans la page **spécifier le bord hérité** , assurez-vous que la liste des serveurs Edge est vide. S’il ne s’agit pas de la liste, appuyez sur le bouton **supprimer** pour supprimer tous les serveurs de périphérie hérités, puis cliquez sur **suivant**.
    
    ![Assistant Fusion-topologie-définir la page de configuration du bord] (images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Assistant Fusion-topologie-définir la page de configuration du bord")  

5.  Dans la page **Specify Internal SIP port Setting** , cliquez sur **Next (suivant**).

6.  Dans la page **Résumé** , cliquez sur **suivant** pour commencer à fusionner les topologies afin de supprimer le site hérité.

7.  Dans la colonne **État** , assurez-vous que la valeur est **succès** , puis cliquez sur **Terminer** pour fermer l’Assistant.

8.  Dans le volet gauche du générateur de topologie, développez le BackCompatSite et assurez-vous qu’aucun serveur n’est répertorié.

9.  Cliquez avec le bouton droit sur le **BackCompatSite**, puis cliquez sur **supprimer**.

10. Dans **Générateur de topologie**, sélectionnez le **serveur Lync**le plus en tête de nœud.

11. Dans le menu **action** , sélectionnez la **topologie de publication** , puis cliquez sur **suivant**.

12. Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant.

</div>

</div>

<span> </span>

</div>

</div>

</div>

