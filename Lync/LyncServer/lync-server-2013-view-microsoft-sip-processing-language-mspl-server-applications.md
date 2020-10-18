---
title: Afficher les applications serveur MSPL (Microsoft SIP Processing Language)
description: Afficher les applications serveur MSPL (Microsoft SIP Processing Language).
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d844acf542546a668c4fc086a07cd6a7bb4a8f5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577070"
---
# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Afficher les applications serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-09-26_

Une application serveur MSPL (Microsoft SIP Processing Language) est une application script uniquement qui utilise un langage de script au lieu de l’API 2010 de Microsoft Lync. Outre la capacité de contrôler avec une plus grande précision les comportements de filtrage et proxy, le langage MSPL offre un procédé qui permet de répartir des messages spécifiques vers des applications SIP fondées sur des transactions. Le langage MSPL est plus particulièrement utilisé pour le filtrage et le routage des messages SIP. Les applications MSPL s’exécutent dans le même processus que le module UserServices, tandis qu’un programme basé sur l’API 2010 de Lync s’exécute dans un processus distinct.

Vous pouvez utiliser la page **application serveur** du groupe **topologie** du panneau de configuration Lync Server pour afficher la liste des applications serveur MSPL qui s’exécutent sur les serveurs frontaux dans votre environnement Lync Server 2013. La liste affiche les scripts disponibles pour chaque pool et indique s’ils sont activés ou critiques. Les scripts sont exécutés dans l’ordre où ils apparaissent dans la liste.

Ces scripts comportent les éléments suivants :

  - ClientVersionFilter permet à l’administrateur de spécifier la version des clients pris en charge dans un pool. Le filtre de version du client vérifie la version du client et peut soit empêcher le client de se connecter, soit présenter à l’utilisateur un message indiquant qu’il utilise un client non pris en charge. Ce filtre peut également être configuré pour afficher un message contenant l’URL d’accès à la dernière version téléchargeable du client.

  - TranslationService permet de convertir un numéro qu’un utilisateur compose vers un numéro E.164, conformément aux règles de normalisation définies par l’administrateur. Pour plus d’informations, consultez la rubrique [règles de conversion dans Lync Server 2013](lync-server-2013-translation-rules.md).

  - IncomingFederation impose la validation de la fédération au niveau du locataire pour les messages entre locataires et entrants en provenance de déploiements externes.

  - UserServices est le composant de serveur d’inscriptions SIP, de présence et de conférence d’un serveur frontal. Il propose des fonctionnalités très intégrées de messagerie instantanée, de présence et de conférence greffées sur le proxy SIP.

  - InterClusterRouting est chargé du routage des appels vers le pool de serveurs d’inscriptions principal de l’appelé. Pour plus d’informations, consultez la rubrique [composants voix sur les serveurs frontaux pour Lync server 2013](lync-server-2013-front-end-server-voip-components.md).

  - IIMFilter (filtre de message instantané intelligent) bloque les messages qui contiennent des URL interactives ou qui tentent de lancer des transferts de fichiers. IIMFilter vérifie également la version du client pour le compte du serveur. IIMFilter affecte les transferts de fichiers qui sont lancés à l’aide de Lync Server ou de Communicator. Par défaut, les liens interactifs sont désactivés en ajoutant un caractère de soulignement avant le premier caractère du lien. Un administrateur peut modifier ce comportement afin que le lien soit bloqué, auquel cas les messages qui contiennent des URL interactives ou qui tentent de lancer un transfert de fichier sont bloqués par le serveur pour atteindre leurs destinations prévues. IIMFilter est installé sur tous les serveurs exécutant Lync Server, à l’exception des serveurs proxy et des serveurs d’archivage.

  - UserPinService sert à vérifier les codes confidentiels dans le cadre des conférences rendez-vous.

  - DefaultRouting est l’application de routage par défaut pour les serveurs exécutant Lync Server. Elle est activée par défaut. L’application de routage est installée sur tous les serveurs Standard Edition et Enterprise Edition.

  - ExumRouting achemine les appels vers la messagerie unifiée Exchange Server. ExumRouting détermine le serveur de messagerie unifiée Exchange approprié vers lequel acheminer l’appel en présence d’un nouveau message vocal à déposer. ExumRouting gère également d’autres aspects d’intégration de la messagerie unifiée Exchange, notamment le routage vers le standard automatique et l’accès abonné.

  - OutboundRouting détermine la passerelle qui achemine un appel vers un numéro de téléphone en fonction du numéro composé et de l’autorisation de numérotation de l’utilisateur. OutboundRouting gère également le réacheminement des appels si une passerelle n’est pas en mesure de traiter un appel.

  - QoEAgent réceptionne les rapports de données de qualité de l’expérience (QoE) en provenance des systèmes d’extrémité par le biais de demandes de service SIP, puis transmet les données à la file d’attente de destination sur le serveur de surveillance ou à des consommateurs tiers via HTTP POST. Pour plus d’informations, reportez-vous à la rubrique [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).

  - OutgoingFederation impose la validation de la fédération au niveau du locataire pour les messages à destination d’un déploiement externe ciblé.

  - AcpRouting redirige via proxy les demandes INVITE les demandes destinées au fournisseur de services d’audioconférence vers la passerelle de ce dernier.

Les scripts exécutés sur des serveurs Edge comprennent les éléments suivants :

  - IIMFilter

  - OptionsHandler répond aux demandes entrantes OPTIONS par **200 OK** si la demande est destinée au serveur actuel. Cet élément est utilisé dans le cadre de la validation des topologies.

<div>

## <a name="see-also"></a>Voir aussi


[Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Marquer une application MSPL (Microsoft SIP Processing Language) comme critique ou non critique dans Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

