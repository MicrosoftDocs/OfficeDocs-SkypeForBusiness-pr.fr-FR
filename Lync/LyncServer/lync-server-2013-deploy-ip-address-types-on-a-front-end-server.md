---
title: 'Lync Server 2013 : Déploiement des types d’adresses IP sur un serveur frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f70ff3098f11cbb3d3b04602dca9c12a4998a367
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a>Déploiement des types d’adresses IP sur un serveur frontal pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-07-28_

À l’aide du générateur de topologie, suivez les étapes décrites dans la procédure ci-dessous pour déployer des types d’adresse IP sur un serveur frontal.

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Pour déployer des types d’adresses IP sur un serveur frontal

1.  Sous **Pools frontaux Enterprise Edition**, cliquez avec le bouton droit sur le serveur d’un pool, puis sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**.)

2.  Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.
    
    **Boîte de dialogue Modifier les propriétés du pool de serveurs frontaux**
    
    ![Boîte de dialogue Modifier les propriétés du serveur frontal](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Boîte de dialogue Modifier les propriétés du serveur frontal")
    
      - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser.
        
        <div>
        

        > [!NOTE]  
        > Cette option est recommandée pour les configurations IP version 6 (IPv6).

        
        </div>
    
      - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour **Adresse IP principale**.
    
      - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
    
      - **Adresse IP RTC** L’installation de cartes d’interface réseau supplémentaires (NIC) s pour la prise en charge de la configuration d’adresse IP RTC pour Lync Server 2013 n’est pas prise en charge sur les rôles de serveur de médiation colocalisés. Pour plus d’informations sur les configurations de carte réseau prises en charge pour Lync Server 2013, voir [plates-formes matérielles pour Lync server 2013](lync-server-2013-server-hardware-platforms.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

