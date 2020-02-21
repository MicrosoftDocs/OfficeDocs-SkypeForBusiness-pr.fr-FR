---
title: Supprimer BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d41d333e834dba34da2a1a04854571d721e94e38
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a>Supprimer BackCompatSite

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Une fois tous les pools désactivés et tous les serveurs Edge désinstallés, exécutez l’Assistant Fusion du Générateur de topologie pour supprimer **BackCompatSite**.

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a>Pour supprimer le site BackCompat à partir du Générateur de topologie

1.  Ouvrez un déploiement existant à partir du Générateur de topologie.

2.  Dans le menu **Actions**, cliquez sur **Fusionner la topologie 2007 R2**.

3.  Cliquez sur **Suivant** pour continuer.

4.  Dans la page **Spécifier la configuration Edge héritée**, vérifiez que la liste des serveurs Edge est vide. Si elle ne l’est pas, utilisez le bouton **Supprimer** pour supprimer tous les serveurs Edge hérités, puis cliquez sur **Suivant**.
    
    ![Assistant fusion de topologies, spécifier la page Configuration du serveur Edge](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Assistant fusion de topologies, spécifier la page Configuration du serveur Edge")  

5.  Dans la page **Spécifier le port SIP interne**, cliquez sur **Suivant**.

6.  Sur la page **Résumé** , cliquez sur **suivant** pour commencer à fusionner les topologies afin de supprimer le site hérité.

7.  Dans la colonne **Statut**, vérifiez que la valeur est **Opération réussie**, puis cliquez sur **Terminer** pour fermer l’Assistant.

8.  Dans le volet de gauche du Générateur de topologie, développez BackCompatSite et vérifiez qu’aucun serveur n’est répertorié.

9.  Cliquez avec le bouton droit sur **BackCompatSite**, puis cliquez sur **Supprimer**.

10. Dans le **Générateur de topologie**, sélectionnez le nœud de niveau supérieur **Lync Server**.

11. Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.

12. Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.

</div>

</div>

<span> </span>

</div>

</div>

</div>

