---
title: 'Lync Server 2013 : publication de la topologie mise à jour'
description: 'Lync Server 2013 : Publiez la topologie mise à jour.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c27cca2eae86eadaf1ff37e2c3520eaec3f86c98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571690"
---
# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Publier la topologie mise à jour dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Après avoir mis à jour votre topologie dans le générateur de topologie, vous devez publier la topologie dans le magasin central de gestion avant de pouvoir configurer et utiliser le serveur de conversation permanente. Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.

<div>

## <a name="to-publish-an-updated-topology"></a>Pour publier une topologie mise à jour

Avant de publier votre topologie, installez les bases de données pour le serveur de conversation permanente. Utilisez le générateur de topologie pour installer des bases de données en sélectionnant **action** et **installer la base de données**.

1.  Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe **administrateurs du domaine** et du groupe **RTCUniversalServerAdmins** et qui dispose des autorisations contrôle total (en lecture, écriture et modification) sur le magasin de fichiers à utiliser pour le magasin de fichiers du serveur de conversation permanente (afin que le générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaire (DACL) requises) ou un compte avec des droits d’utilisateur équivalents.

2.  Démarrez le Générateur de topologie. Sélectionnez **Télécharger la topologie à partir du déploiement existant** ou **Ouvrir une topologie depuis un fichier local** si vous l’avez enregistrée localement.

3.  Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **publier la topologie**.

4.  Dans la page **Publier la topologie**, cliquez sur **Suivant**.

5.  Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!IMPORTANT]  
    > Après avoir publié la topologie, vous devez configurer la prise en charge du serveur de conversation permanente pour pouvoir archiver le contenu.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

