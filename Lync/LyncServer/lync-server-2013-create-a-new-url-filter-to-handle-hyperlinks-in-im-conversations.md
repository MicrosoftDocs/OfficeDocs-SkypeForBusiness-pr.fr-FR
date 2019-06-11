---
title: Créer un nouveau filtre d’URL pour gérer les liens hypertexte dans les conversations par messagerie instantanée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new URL filter to handle hyperlinks in IM conversations
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182590(v=OCS.15)
ms:contentKeyID: 48185426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f8f9a06dd80f87f2758269ddd2d468aeae2014d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-url-filter-in-lync-server-2013-to-handle-hyperlinks-in-im-conversations"></a>Créer un nouveau filtre d’URL dans Lync Server 2013 pour gérer les liens hypertexte dans les conversations par messagerie instantanée

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-26_

Outre la modification du filtre d’URL global, vous pouvez configurer des filtres d’URL personnalisés pour des sites individuels au sein de votre déploiement 2013 Lync Server. Pour plus d’informations sur le filtrage d’URL, voir [configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

<div>

## <a name="to-create-a-new-url-filter"></a>Pour créer un nouveau filtre d’URL

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **messagerie instantanée et présence**, puis cliquez sur **filtre d’URL**.

4.  Dans la page de **filtre d’URL** , cliquez sur **nouveau**.

5.  Dans **Sélectionner un site**, cliquez sur le site pour lequel vous souhaitez créer le filtre d’URL, puis cliquez sur **OK**.

6.  Dans la boîte de dialogue **nouveau filtre d’URL** , activez la case à cocher **activer** le filtrage d’URL pour le site.

7.  Pour bloquer toute URL active contenant un fichier avec une extension répertoriée sous **extensions de type de fichier à bloquer** dans la boîte de réception **modifier le filtre de fichier**, activez la case à cocher bloquer les **URL avec l’extension de fichier** .

8.  Dans la zone de liste déroulante des **liens hypertexte** , cliquez sur l’option qui correspond à la manière dont vous souhaitez gérer les URL dans les conversations par messagerie instantanée.
    
    La boîte de **dialogue autoriser le message** permet d’envoyer un message d’avertissement à l’utilisateur lors de l’envoi de liens hypertexte qui peuvent être envoyés.

9.  Cliquez sur **Valider**.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du transfert de fichiers et du filtrage d’URL pour la messagerie instantanée dans Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Créer un filtre de transfert de fichiers dans Lync Server 2013 pour un site spécifique](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Modifier le filtre de transfert de fichiers par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-file-transfer-filter.md)  


[Modifier le filtre d’URL par défaut dans Lync Server 2013](lync-server-2013-modify-the-default-url-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

