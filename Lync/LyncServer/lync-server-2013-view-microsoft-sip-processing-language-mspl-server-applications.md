---
title: Afficher des applications de serveur MSPL (Microsoft SIP Processing Language)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2a8aea4b412d2d744c42d659d2414a93c8435e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Afficher des applications de serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-09-26_

Une application serveur Microsoft SIP Processing Language (MSPL) est une application de script uniquement qui utilise un langage de script au lieu de l’API 2010 Microsoft Lync. MSPL fournit un contrôle plus précis sur le filtrage et les comportements de proxy, en plus d’une installation permettant de distribuer des messages spécifiques aux applications SIP en fonction des transactions. Le MSPL est utilisé spécifiquement pour filtrer et acheminer les messages SIP. Les applications MSPL s’exécutent dans le même processus que le module UserServices, tandis qu’un programme basé sur l’API 2010 Lync s’exécute dans un processus distinct.

Vous pouvez utiliser la page de l' **application serveur** dans le groupe **topologie** du panneau de configuration de Lync Server pour afficher une liste des applications serveur MSPL qui s’exécutent sur des serveurs frontaux dans votre environnement Lync Server 2013. La liste affiche les scripts disponibles pour chaque liste, ainsi que leur activation ou leur importance critique. Les scripts s’exécutent dans l’ordre dans lequel ils apparaissent.

Ces scripts incluent les éléments suivants:

  - ClientVersionFilter fournit à l’administrateur un moyen de spécifier la version des clients pris en charge par un pool. Le filtre de version du client vérifie la version du client et peut soit empêcher le client de se connecter, soit en présenter un message indiquant qu’il utilise un client qui n’est pas pris en charge. Le filtre de version du client peut également être configuré pour afficher un message destiné à l’utilisateur, qui contient l’URL de la version téléchargeable la plus récente du client.

  - TranslationService convertit un nombre qu’un utilisateur compose vers un numéro E. 164 conformément aux règles de normalisation définies par l’administrateur. Pour plus d’informations, voir [règles de traduction dans Lync Server 2013](lync-server-2013-translation-rules.md).

  - IncomingFederation applique la validation de la Fédération au niveau du client pour les messages entrants et inter-locataire provenant de déploiements externes.

  - UserServices est le composant d’inscription SIP, de présence et de conférence d’un serveur frontal. Ce service offre des fonctionnalités de messagerie instantanée, de présence et de conférence étroitement intégrées, intégrées au-dessus du proxy SIP.

  - InterClusterRouting est responsable du routage des appels vers le pool d’inscriptions principal de l’appelant. Pour plus d’informations, reportez-vous à la rubrique [composants VoIP serveur front-end pour Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).

  - IIMFilter (filtre de messages instantanés intelligents) bloque les messages qui contiennent des URL cliquables ou qui tentent d’initialiser des transferts de fichiers. IIMFilter vérifie également la version du client pour le compte du serveur. IIMFilter affecte les transferts de fichiers initiés via Lync Server ou Communicator. Par défaut, les liens hypertexte peuvent être désactivés en ajoutant un trait de soulignement avant le premier caractère du lien. Un administrateur peut modifier ce comportement de manière à ce que le lien soit bloqué, auquel cas les messages qui contiennent des URL sur lesquelles vous pouvez cliquer ou qui essaient de lancer un transfert de fichier sont bloqués par le serveur pour atteindre les destinations prévues. IIMFilter est installé sur tous les serveurs exécutant Lync Server, à l’exception des serveurs proxy et des serveurs d’archivage.

  - UserPinService est utilisé pour vérifier les codes confidentiels (pin) de l’utilisateur pour les conférences rendez-vous.

  - DefaultRouting est l’application de routage par défaut pour les serveurs exécutant Lync Server. Elle est activée par défaut. L’application de routage est installée sur tous les serveurs Standard Edition et Enterprise Edition.

  - ExumRouting route les appels vers la messagerie unifiée Exchange Server. ExumRouting détermine le serveur Exchange UM approprié pour diriger l’appel lorsqu’un nouveau message vocal doit être déposé. ExumRouting gère également d’autres aspects d’intégration de la messagerie unifiée Exchange, notamment le routage vers le standard automatique et l’accès de l’abonné.

  - OutboundRouting détermine la passerelle qui route un appel vers un numéro de téléphone en fonction du numéro composé et de l’autorisation de numérotation de l’utilisateur. OutboundRouting gère également le reroutage des appels si une passerelle ne peut pas traiter un appel.

  - QoEAgent reçoit des rapports de données de qualité d’utilisation (QoE) de points de terminaison par le biais de demandes de SERVICE SIP et envoie les données à la file d’attente de destination sur le serveur de surveillance ou auprès de clients tiers à l’aide de HTTP POST. Pour plus d’informations, reportez-vous à la rubrique [déploiement de la surveillance dans Lync Server 2013](lync-server-2013-deploying-monitoring.md).

  - OutgoingFederation applique la validation de la Fédération au niveau du client pour les messages dirigés vers un déploiement externe ciblé.

  - Les proxys AcpRouting invitent les demandes destinées au fournisseur de services d’audioconférence à la passerelle du fournisseur de services d’audioconférence.

Les scripts qui s’exécutent sur des serveurs Edge incluent les éléments suivants:

  - IIMFilter

  - OptionsHandler répond aux demandes d’OPTIONS entrantes avec **200 OK** si la requête est destinée au serveur actuel. Cette opération est utilisée pour la validation de la topologie.

<div>

## <a name="see-also"></a>Voir aussi


[Activer ou désactiver une application serveur MSPL (Microsoft SIP Processing Language) dans Lync Server 2013](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Marquer une application Microsoft SIP Processing Language (MSPL) comme critique ou non critique dans Lync Server 2013](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

