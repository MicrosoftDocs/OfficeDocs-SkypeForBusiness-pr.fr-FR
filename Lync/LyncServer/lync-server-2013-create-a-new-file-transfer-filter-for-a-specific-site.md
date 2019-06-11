---
title: 'Lync Server 2013: créer un nouveau filtre de transfert de fichiers pour un site spécifique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new file transfer filter for a specific site
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182589(v=OCS.15)
ms:contentKeyID: 48185577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ddb23081acba6eb208607a0bacddb7b403468b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-file-transfer-filter-in-lync-server-2013-for-a-specific-site"></a>Créer un filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-18_

Outre la modification du filtre global de transfert de fichiers, vous pouvez configurer des filtres de transfert de fichier personnalisés pour des sites spécifiques au sein de votre déploiement 2013 Lync Server. Pour plus d’informations sur le filtrage du transfert de fichiers, voir [configurer le transfert de fichiers et le filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-file-transfer-filter-for-a-specific-site"></a>Pour créer un filtre de transfert de fichiers pour un site spécifique

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **messagerie instantanée et présence** , puis cliquez sur **filtre de fichiers**.

4.  Dans la page **filtre de fichier** , cliquez sur **nouveau**.

5.  Dans la boîte de dialogue **Sélectionner un site** , cliquez sur le site pour lequel vous souhaitez créer le filtre de transfert de fichiers, puis cliquez sur **OK**.

6.  Dans le **nouveau filtre de fichier**, activez la case à cocher **activer le filtre de fichiers** .

7.  Dans la zone de liste déroulante **transfert de fichier** , cliquez sur **bloquer tout** ou **bloquer des types de fichiers spécifiques**.

8.  Si vous avez cliqué sur **bloquer tout**, passez à l’étape 10.

9.  Si vous avez cliqué sur **bloquer des types de fichiers spécifiques**, procédez comme suit:
    
    1.  Cliquez sur **Sélectionner** pour modifier la liste par défaut des extensions de type de fichier que vous voulez bloquer.
    
    2.  Dans la boîte de dialogue **Sélectionner le type de fichier** , sélectionnez les types de fichiers que vous souhaitez bloquer ou autoriser en ajoutant ou en supprimant leurs extensions des catégories sous extensions de type de **fichier**.
    
    3.  Si vous ne voyez pas l’extension correspondant au type de fichier que vous voulez bloquer, tapez l’extension dans la zone de texte sous **Ajouter des extensions de type de fichier à la liste**, puis cliquez sur **Ajouter**.
    
    4.  Cliquez sur **OK**.

10. Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modifier le filtre d’URL par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

