---
title: 'Lync Server 2013 : vérifier les communications avec un client Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59fcf8398fa012543303f959f4888074f5192470
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>Vérifier les communications avec un client Lync Online dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-08_

Pour permettre aux utilisateurs Lync de votre organisation de communiquer avec les utilisateurs d’un client Microsoft Lync Online 2010, vous devez avoir effectué les étapes suivantes :

  - Respectez tous les éléments prérequis. Cela inclut le déploiement de vos serveurs internes et de périphérie, l’activation de la prise en charge de la Fédération pour votre organisation et la configuration des comptes d’utilisateurs. Pour plus d’informations, reportez-vous à [la rubrique conditions préalables à la Fédération avec un client Lync Online dans Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).

  - Vous avez configuré la prise en charge de l’accès au domaine dans votre déploiement interne. Cela inclut la création d’une entrée de fournisseur d’hôte et la configuration de votre déploiement pour autoriser l’accès à partir du domaine du client Lync Online. Pour plus d’informations, consultez [la rubrique Configurer la prise en charge de la Fédération pour un domaine Lync Online dans Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Vous avez configuré les comptes de vos utilisateurs de sorte qu’ils prennent en charge la fédération. Pour plus d’informations, voir [configurer l’accès utilisateur pour la Fédération avec un client Lync Online dans Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

Une fois que vous avez effectué toutes ces étapes et que l’administrateur du client Lync Online 2010 complète toutes les configurations de leurs services en ligne afin de prendre en charge la Fédération avec votre organisation, vérifiez les communications en testant les communications entre un service interne utilisateur au sein de votre organisation et un utilisateur du client Lync Online. Si la communication échoue, utilisez l’outil de journalisation à partir de votre serveur Edge pour capturer les fichiers journaux et de suivi afin de résoudre le problème. Pour plus d’informations sur l’utilisation de l’outil de journalisation, voir [Open Lync Server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md) dans la documentation des opérations. Pour plus d’informations sur l’outil de journalisation, voir la documentation de l’outil de journalisation [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)Lync Server 2010 dans la bibliothèque TechNet à l’adresse.

</div>

<span> </span>

</div>

</div>

</div>

