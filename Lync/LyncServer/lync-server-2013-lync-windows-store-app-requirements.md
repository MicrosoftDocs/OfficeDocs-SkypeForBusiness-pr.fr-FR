---
title: 'Lync Server 2013 : configuration requise pour les applications Lync Windows Store'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84e4c7c9f4fb07d737b4f384faa5559a69c2392c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Configuration requise pour les applications Lync Windows Store pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-03_

Les organisations disposant d’un déploiement local de Lync Server doivent remplir les conditions suivantes pour prendre en charge l’application Lync du Windows Store.

<div>


> [!NOTE]  
> Pour Lync Server 2010, exécutez la mise à jour cumulative pour Lync Server 2010 : février 2012 (disponible à l’adresse <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) ou version ultérieure sur tous les serveurs. Pour permettre aux utilisateurs de participer à des réunions, exécutez la mise à jour cumulative pour Lync Server 2010 : octobre 2012 (disponible à l’adresse <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) sur les serveurs.



</div>

  - Activer le service de découverte automatique, Lync Web App et les services de ticket Web sur le serveur.

  - Activez l’authentification par certificat sur le serveur frontal ou le pool frontal. (Le processus d’enregistrement de l’utilisateur sur le serveur frontal ou le pool frontal est souvent appelé serveur d’inscriptions.) Pour plus d’informations, consultez la rubrique [créer des paramètres de configuration du serveur d’inscriptions dans Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

  - Publiez les enregistrements de ressource d’alias DNS (CNAMe) pour le service de découverte automatique.

  - Il n’est plus nécessaire de s’assurer que le point de distribution de liste de révocation de certificats (CDP) pour les certificats délivrés à Lync Server pointe vers une ressource HTTP au lieu d’une ressource LDAP. Toutefois, assurez-vous que les mises à jour Windows les plus récentes sont installées sur les ordinateurs clients.

  - Configurez des proxys HTTP dans l’entreprise pour autoriser le trafic HTTP associé à Lync Server.Ajoutez des exceptions pour les services de découverte automatique, Lync Web App et webticket, si nécessaire.

  - Sur les clients, installez Windows 8,1 et la dernière version de Lync Windows Store App pour résoudre un problème de connexion qui se produit généralement lorsque vous utilisez plusieurs domaines (par exemple, lorsque l’URI SIP est **usera@domainZ.com** mais que le serveur Edge est **SIP.domainX.com**).

Si votre organisation s’abonne à Lync Online ou Office 365 et que vous utilisez votre propre nom de domaine, vous devez suivre quelques étapes supplémentaires pour configurer votre réseau pour la découverte automatique des serveurs Lync. Les exigences de configuration réseau sont les mêmes pour les applications Lync Windows Store et Lync sur les appareils mobiles. Suivez les instructions « configurer votre réseau » dans l’article wiki Office 365 « configurer des appareils Lync mobile » disponible à l’adresse [https://go.microsoft.com/fwlink/?LinkId=271822](https://go.microsoft.com/fwlink/?linkid=271822).

<div>

## <a name="see-also"></a>Voir aussi


[Déploiement de l’application Lync Windows Store dans Lync Server 2013](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

