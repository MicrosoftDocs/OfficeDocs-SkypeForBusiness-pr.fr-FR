---
title: 'Lync Server 2013 : Planification des certificats de serveur Edge'
TOCTitle: Planification des certificats de serveur Edge
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413010(v=OCS.15)
ms:contentKeyID: 49299302
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification des certificats de serveur Edge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-05_

La création de certificat pour Edge est simplifiée dans Lync Server 2013.

**Diagramme de certificats pour le serveur Edge**

![Diagramme des certificats](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "Diagramme des certificats")

Créez un certificat public unique, vérifiez que vous disposez d’une clé privée exportable définie pour le certificat, et affectez-le aux interfaces externes du serveur Edge à l’aide de l’Assistant Certificat :

> [!IMPORTANT]  
> Les certificats génériques ne sont pas pris en charge dans Lync Server, sauf s’ils sont utilisés pour résumer des URL simples via le proxy inverse. Vous devez définir des noms SAN distincts pour chaque nom de domaine SIP, service Edge de conférence web, service Edge A/V et domaine XMPP proposés par votre déploiement.

> [!NOTE]  
> Introduits dans Lync Server 2013, les certificats d’authentification audio/vidéo temporaires précédant l’expiration du certificat actuel requièrent une planification supplémentaire. Au lieu d’un certificat utilisé à des fins diverses pour l’interface externe du serveur Edge, vous aurez besoin de deux certificats : l’un sera affecté au service Edge d’accès et au service Edge de conférence web, tandis que l’autre sera affecté au service Edge A/V. Pour obtenir des informations supplémentaires, reportez-vous à <a href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate">Préparation de certificats AV et OAuth dans Lync Server 2013 à l’aide du paramètre -Roll dans l’applet de commande Set-CsCertificate</a>

> [!IMPORTANT]  
> Dans le cas d’un pool de serveurs Edge, vous devez exporter le certificat avec la clé privée à chaque serveur Edge et affecter le certificat à chaque service serveur Edge. Procédez de la même façon pour le certificat serveur Edge, en exportant le certificat avec la clé privée et en l’affectant à chaque interface interne de serveur Edge.

  - Vérifiez que vous disposez d’une clé privée exportable affectée pour le certificat.

  - service Edge d’accès (désigné sous le nom de **Serveur Edge d’accès SIP externe** dans l’Assistant Certificat)

  - service Edge de conférence web (désolé sous le nom de **Serveur Edge de conférence web externe** dans l’Assistant Certificat)

  - Service d’authentification A/V (désigné comme **Serveur Edge A/V externe** dans l’Assistant Certificat)

Créez un certificat interne unique doté d’une clé privée exportable, copiez-le et affectez-le aux interfaces internes du serveur Edge suivantes :

  - Serveur Edge (désigné comme **Serveur Edge interne** dans l’Assistant Certificat)

> [!IMPORTANT]  
> Vous pouvez utiliser des certificats distincts et séparés pour chaque service serveur Edge. Cela peut être le cas si vous souhaitez utiliser la nouvelle fonctionnalité de certificat propagé pour le certificat service Edge A/V. Dans le cas de cette fonctionnalité, Le découplage du certificat service Edge A/V du service Edge d’accès et du service Edge de conférence web est recommandé. Si vous choisissez de demander, acquérir et affecter des certificats distincts pour chaque service, vous devez demande que la clé privée soit exportable pour le service Edge A/V (rappel : il s’agit du service d’authentification A/V) et d’affecter le même certificat à l’interface externe Edge A/V sur chaque serveur Edge.

## Voir aussi

#### Tâches

[Préparation de certificats AV et OAuth dans Lync Server 2013 à l’aide du paramètre -Roll dans l’applet de commande Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)  

#### Concepts

[Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

