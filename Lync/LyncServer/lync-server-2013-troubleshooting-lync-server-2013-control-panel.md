---
title: 'Lync Server 2013: résolution des problèmes du panneau de configuration de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 943f2ab5f0fe808d1bf5e10cf8b451ac1df2575b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Résolution des problèmes liés à Lync Server 2013 Control Panel

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-07-28_

Cette rubrique fournit des informations et des procédures qui peuvent vous aider à résoudre les problèmes d’accès à Lync Server 2013 panneau de configuration.

<div>

## <a name="internet-browser-requirements"></a>Configuration requise pour le navigateur Internet

Le panneau de configuration de Lync Server nécessite que le plug-in de navigateur Microsoft Silverlight version 4.0.50524.0 ou la version la plus récente soit installée. Si Silverlight n’est pas installé ou si vous avez installé une version antérieure, suivez les instructions du message pour installer la version requise.

<div>


> [!NOTE]  
> D’autres configurations logicielles requises pour le panneau de configuration de Lync Server sont relatives au système d’exploitation sur lequel le panneau de configuration de Lync Server et tous les autres outils d’administration de Lync Server 2013 peuvent être installés. Pour plus d’informations, reportez-vous à la <A href="lync-server-2013-server-and-tools-operating-system-support.md">prise en charge du système d’exploitation serveur et outils dans Lync Server 2013</A> dans la documentation de prise en charge.



</div>

Si votre navigateur Web bloque l’installation de Silverlight en raison de considérations relatives à la sécurité, ajoutez l’URL (Uniform Resource Locator) qui ouvre le panneau de configuration de Lync Server à la liste des sites de confiance. Dans les paramètres de sécurité d’Internet Explorer, assurez-vous que l’option **exécuter les contrôles ActiveX et les plug-ins** est définie sur **activé**. Pour plus d’informations [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060), reportez-vous à. Par ailleurs, assurez-vous que le navigateur est configuré pour utiliser SSL 3,0.

Si le navigateur Internet est configuré pour utiliser un serveur proxy, assurez-vous que le navigateur est configuré pour ignorer le serveur proxy pour les sites qui sont automatiquement détectés comme des sites internes. Vous pouvez ou ajouter l’adresse dans la liste des exceptions du navigateur dans les paramètres de configuration du serveur proxy.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>Exigences relatives aux enregistrements DNS et aux certificats pour l’URL d’accès administratif

Si vous avez configuré une URL simple permettant d’accéder au panneau de configuration de Lync Server, assurez-vous également de configurer l’enregistrement de ressources (A) hôte DNS (Domain Name System) et le certificat nécessaires pour utiliser cette URL d’accès administratif. Si vous modifiez l’URL de base à tout moment, assurez-vous que la modification est répercutée dans l’enregistrement DNS approprié et le certificat et que vous exécutez le fichier *Enable-CsComputer* sur chaque réalisateur et serveur frontal pour inscrire la modification. Pour plus d’informations, reportez-vous aux rubriques suivantes dans la documentation de planification:

  - [Planification des URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Enregistrements DNS requis pour les URL simples dans Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Pour obtenir des procédures pas à pas pour configurer l’URL d’accès administratif, voir [modifier ou configurer des URL simples dans Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) dans la documentation de déploiement.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Configuration requise pour Internet Information Services (IIS)

Le panneau de configuration de Lync Server est l’un des composants de Lync Server 2013 qui nécessite Internet Information Services (IIS). Vérifiez en particulier que les fonctionnalités de redirection HTTP et d’authentification Windows sont activées et que le service de publication World Wide Web (W3SVC) est en cours d’exécution.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Dépendance du service de publication World Wide (service Windows)

Lorsque le service de publication World Wide Web est arrêté, vous ne pouvez pas accéder au panneau de configuration de Lync Server. Vous pouvez redémarrer le service à l’aide de la console de gestion des services Windows (MMC).

**Pour démarrer le service de publication World Wide Web**

1.  Ouvrez une session sur l’ordinateur sur lequel le service de publication World Wide Web est installé dans le cadre de Internet Information Services (IIS).

2.  Cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **services**.

3.  Cliquez avec le bouton droit sur **service de publication World Wide Web**, puis cliquez sur **Démarrer**.

</div>

<div>

## <a name="application-pool-mode"></a>Mode pool d’applications

Configurer IIS de manière à ce que le pool d’applications CsManagementAppPool utilise le compte de service réseau en tant qu’identité de modèle de processus.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Droits d’utilisateur et autorisations

Vous devez vous connecter au panneau de configuration de Lync Server à l’aide d’un compte de domaine membre du groupe CsAdministrator ou en utilisant un compte auquel vous avez délégué des droits d’utilisateur et des autorisations. Vous ne pouvez pas vous connecter au panneau de configuration de Lync Server à l’aide d’un compte d’ordinateur local. Pour plus d’informations sur la délégation de tâches d’administration par le biais d’un contrôle d’accès basé sur les rôles (RBAC), voir [planification du contrôle d’accès basé sur les rôles dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.

Si vous utilisez une URL simple pour accéder au panneau de configuration de Lync Server, assurez-vous que les serveurs Web sont ajoutés aux groupes RTCUniversalServerAdmins et RTCUniversalUserAdmins.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Outils d’administration de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

