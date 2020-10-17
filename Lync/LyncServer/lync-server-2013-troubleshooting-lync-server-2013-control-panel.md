---
title: 'Lync Server 2013 : résolution des problèmes dans le panneau de configuration Lync Server 2013'
description: 'Lync Server 2013 : résolution des problèmes dans le panneau de configuration Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c3559c26b7b0a8d715563665c4b9a57e5999156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549020"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a>Dépannage du panneau de configuration Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-07-28_

Cette rubrique fournit des informations et des procédures qui peuvent vous aider à résoudre les problèmes liés à l’accès au panneau de configuration Lync Server 2013.

<div>

## <a name="internet-browser-requirements"></a>Configuration requise du navigateur Internet

Le panneau de configuration Lync Server nécessite l’installation du plug-in de navigateur Microsoft Silverlight version 4.0.50524.0 ou de la dernière version. Si Silverlight n’est pas installé ou si une version antérieure est installée, suivez les instructions du message pour installer la version requise.

<div>


> [!NOTE]  
> La section autres logiciels requis pour le panneau de configuration Lync Server se rapporte au système d’exploitation sur lequel le panneau de configuration Lync Server et tous les autres outils d’administration Lync Server 2013 peuvent être installés. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-server-and-tools-operating-system-support.md">serveur and Tools Operating System Support in Lync Server 2013</A> dans la documentation de prise en charge.



</div>

Si votre navigateur Internet bloque l’installation de Silverlight en raison de considérations de sécurité, ajoutez l’URL (Uniform Resource Locator) qui ouvre le panneau de configuration Lync Server à la liste des sites de confiance. Dans les paramètres de sécurité d’Internet Explorer, vérifiez que **Exécuter les contrôles ActiveX et les plugins** est défini comme **Activé**. Pour plus d’informations, reportez-vous à [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) . De plus, vérifiez que le navigateur est configuré pour utiliser SSL 3.0.

Si le navigateur Internet est configuré de sorte d’utiliser un serveur proxy, vérifiez qu’il est configuré pour contourner le serveur proxy pour les sites qui sont automatiquement détectés comme des sites internes. Vous pouvez aussi ajouter l’adresse à la liste d’exception du navigateur dans les paramètres de configuration du serveur proxy.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>Spécifications des certificats et enregistrements DNS pour l’URL d’accès administratif

Si vous avez configuré une URL simple pour accéder au panneau de configuration Lync Server, vérifiez que vous avez également configuré l’enregistrement de ressource A (Domain Name System) statique et le certificat nécessaire à l’utilisation de cette URL d’accès administratif. Si vous modifiez l’URL de base à tout moment, assurez-vous que la modification est reflétée dans l’enregistrement DNS et le certificat appropriés et que vous exécutez l' *CsComputer* sur chaque directeur et serveur frontal pour enregistrer la modification. Pour des détails, consultez les rubriques suivantes dans la documentation de planification :

  - [Planification des URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Configuration DNS requise pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Pour obtenir des procédures pas à pas sur la configuration de l’URL d’accès administratif, voir [modifier ou configurer des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) dans la documentation de déploiement.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Exigences relatives aux services Internet (IIS)

Le panneau de configuration Lync Server est l’un des composants de Lync Server 2013 qui nécessitent Internet Information Services (IIS). Vérifiez en particulier que les fonctionnalités de redirection HTTP et d’authentification Windows sont activées, et que le service de publication World Wide Web (W3SVC) est exécuté.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Dépendance du service de publication World Wide Web (Service Windows)

Lorsque le service de publication sur le Web est arrêté, vous ne pouvez pas accéder au panneau de configuration Lync Server. Vous pouvez redémarrer le service en utilisant la console MMC (Microsoft Management Console) Services Windows.

**Pour démarrer le service de publication World Wide Web**

1.  Ouvrez une session sur l’ordinateur sur lequel le service de publication World World-Web est installé dans le cadre d’Internet Information Services (IIS).

2.  Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Services**.

3.  Cliquez avec le bouton droit sur le **Service de publication World Wide Web**, puis cliquez sur **Démarrer**.

</div>

<div>

## <a name="application-pool-mode"></a>Mode Pool d’applications

Configurez IIS de sorte que le pool d’applications CsManagementAppPool utilise le compte Service réseau pour son identité de modèle de processus.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Droits et autorisations de l’utilisateur

Vous devez vous connecter au panneau de configuration Lync Server à l’aide d’un compte de domaine membre du groupe CsAdministrator ou à l’aide d’un compte auquel vous avez délégué des droits d’utilisateur et des autorisations. Vous ne pouvez pas vous connecter au panneau de configuration Lync Server à l’aide d’un compte d’ordinateur local. Pour plus d’informations sur la délégation de tâches administratives via le contrôle d’accès basé sur un rôle (RBAC), voir [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.

Si vous utilisez une URL simple pour accéder au panneau de configuration Lync Server, vérifiez que les serveurs Web sont ajoutés aux groupes RTCUniversalServerAdmins et RTCUniversalUserAdmins.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Outils d’administration Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

