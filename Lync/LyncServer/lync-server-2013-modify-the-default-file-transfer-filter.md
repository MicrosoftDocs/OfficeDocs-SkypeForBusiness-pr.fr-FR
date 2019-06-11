---
title: 'Lync Server 2013: modifier le filtre de transfert de fichiers par défaut'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default file transfer filter
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521017(v=OCS.15)
ms:contentKeyID: 48184584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 475f6e9b599af9ba6db80fdb174d3b38e5df6b00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-file-transfer-filter-in-lync-server-2013"></a>Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Lync Server 2013 fournit un filtre de transfert de fichiers global qui bloque des types de fichiers spécifiques pendant les activités suivantes relatives aux fichiers dans votre déploiement de Lync Server 2013:

  - Demandes de transfert de fichiers lors des conversations de messagerie instantanée

  - Chargement et téléchargement de fichiers lors de l’utilisation de la fonctionnalité de documentation dans le client Office Live Meeting 2007

  - Lecture de contenu multimédia lors de conférences

En fonction des types de fichiers que vous souhaitez bloquer ou autoriser, vous pouvez utiliser le panneau de configuration de Lync Server pour modifier le filtre global. Pour plus d’informations sur le filtrage du transfert de fichiers, voir [configurer le transfert de fichiers et le filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-modify-the-default-file-transfer-filter"></a>Pour modifier le filtre de transfert de fichiers par défaut

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **messagerie instantanée et présence** , puis cliquez sur **filtre de fichiers**.

4.  Sur la page **filtre de fichiers** , double-cliquez sur le filtre **Global** .

5.  Dans **modifier le filtre de fichier**, activez la case à cocher **activer le filtre de fichiers** .

6.  Dans la zone de liste déroulante **transfert de fichiers** , cliquez sur **bloquer tout** ou **bloquer des types de fichiers spécifiques**.

7.  Si vous avez cliqué sur **bloquer tout**, passez à l’étape 9.

8.  Si vous avez cliqué sur **bloquer des types de fichiers spécifiques**, procédez comme suit:
    
    1.  Cliquez sur **Sélectionner** pour modifier la liste par défaut des extensions de type de fichier que vous voulez bloquer.
    
    2.  Dans **Sélectionner un type de fichier**, sélectionnez les types de fichiers que vous souhaitez bloquer ou autoriser en ajoutant ou en supprimant leurs extensions des catégories sous **extensions de type de fichier**.
    
    3.  Si vous ne voyez pas l’extension correspondant au type de fichier que vous voulez bloquer, tapez l’extension dans la zone de texte sous **Ajouter des extensions de type de fichier à la liste**, puis cliquez sur **Ajouter**.
    
    4.  Cliquez sur **OK**.

9.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Créer un filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  


[Modifier le filtre d’URL par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

