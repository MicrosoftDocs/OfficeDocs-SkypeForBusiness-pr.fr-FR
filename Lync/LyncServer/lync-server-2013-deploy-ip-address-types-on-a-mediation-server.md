---
title: 'Lync Server 2013 : déploiement des types d’adresses IP sur un serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44c8ca531ccb9df74e382068af127d630d5c62b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>Déployer des types d’adresses IP sur un serveur de médiation pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-07-28_

À l’aide du générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur de médiation.

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Pour déployer des types d’adresses IP sur un serveur de médiation

  - Dans le générateur de topologie, sous **pools de médiation**, cliquez avec le bouton droit sur le serveur dans un pool, puis sélectionnez **modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action**)

  - Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.
    
    **Boîte de dialogue Modifier les propriétés pour le pool de serveurs de médiation**
    
    ![Page de propriétés générales de Lync Server avec nom de domaine complet](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Page de propriétés générales de Lync Server avec nom de domaine complet")
    
      - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur.
        
        <div>
        

        > [!NOTE]  
        > Cette option est recommandée pour les configurations IP version 6 (IPv6).

        
        </div>
    
      - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour indiquer une adresse spécifique à utiliser sur le nouveau serveur. Si vous sélectionnez cette option, vous devez entrer une valeur pour l’adresse IP principale.
    
      - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (PSTN). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
    
      - **Adresse IP PSTN** Définir une adresse IP PSTN lorsqu’un serveur de médiation est autonome. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
        
        <div>
        

        > [!NOTE]  
        > L’installation de cartes d’interface réseau (NIC) supplémentaires pour prendre en charge la configuration de l’adresse IP RTC pour Lync Server 2013 n’est pas prise en charge sur les rôles de serveur de médiation colocalisés. Pour plus d’informations sur les configurations NIC prises en charge pour Lync Server 2013, consultez la rubrique <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for Lync server 2013</A>.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

