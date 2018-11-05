---
title: 'Lync Server 2013 : Demande des certificats pour les composants Edge'
TOCTitle: Demande des certificats pour les composants Edge
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398708(v=OCS.15)
ms:contentKeyID: 49298004
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Demande des certificats pour les composants Edge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-07_

Les certificats nécessaires à la prise en charge de l’accès des utilisateurs externes incluent les certificats émis par une autorité de certification publique et les certificats émis par une autorité de certification d’entreprise interne :

  - Les certificats requis pour l’interface externe des serveur Edge et le proxy inverse doivent être émis par une autorité de certification publique.

  - Les certificats requis pour l’interface interne peuvent être émis par une autorité de certification publique ou une autorité de certification d’entreprise interne. Nous vous conseillons d’utiliser une autorité de certification Windows Server 2008 interne, une autorité de certification Windows Server 2008 R2, une autorité de certification Windows Server 2012 ou une autorité de certification Windows Server 2012 R2 pour créer ces certificats afin d’éviter les dépenses liées à l’utilisation de certificats publics.

> [!IMPORTANT]  
> Le traitement des demandes de certificats peut prendre du temps, notamment les demandes effectuées auprès des autorités de certification publiques. Par conséquent, veillez à demander les certificats de vos serveurs Edge suffisamment tôt pour être certain qu’ils seront disponibles lorsque vous commencerez le déploiement de vos composants de serveur Edge. Pour obtenir un résumé des éléments de certificat requis pour les serveurs Edge, reportez-vous à <a href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013</a>.

Même si vous pouvez choisir d’utiliser une autorité de certification publique pour le certificat Edge interne, nous vous conseillons plutôt d’utiliser une autorité de certification d’entreprise interne pour les autres certificats pour en réduire le coût. Pour obtenir le résumé des certificats requis pour les serveurs Edge, reportez-vous à [Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

> [!NOTE]  
> Lorsque vous installez un serveur Edge, le programme d’installation inclut un Assistant Certificat qui simplifie la demande, l’attribution et l’installation de certificats, comme indiqué dans la section <a href="lync-server-2013-set-up-edge-certificates.md">Configuration des certificats de serveur Edge pour Lync Server 2013</a>. Si vous souhaitez demander des certificats avant d’installer un serveur Edge (pour gagner du temps pendant le déploiement réel des composants de serveur Edge), vous pouvez utiliser des serveurs internes tant que vous vous assurez que les certificats sont exportables et contiennent tous les autres noms de sujet requis. Cette documentation ne fournit pas de procédures relatives à l’utilisation de serveurs internes pour la demande de certificats.

## Demander des certificats à une autorité de certification publique

Votre déploiement de serveur Edge nécessite un certificat public unique pour les interfaces externes des serveurs Edge, utilisé pour le service Edge d’accès, le service Edge de conférence web et le service d’authentification A/V. Ce certificat doit disposer d’une clé privée exportable pour s’assurer que le service d’authentification A/V utilise les mêmes clés sur tous les serveurs Edge d’un même pool. Le proxy inverse, utilisé avec Microsoft Internet Security and Acceleration (ISA) Server 2006 ou Microsoft Forefront Threat Management Gateway 2010, nécessite également un certificat public.

## Demander des certificats à partir d’une autorité de certification d’entreprise interne

Les certificats nécessaires à l’interface interne du serveur Edge peuvent être émis par une autorité de certification publique ou interne. L’utilisation d’une autorité de certification interne à l’entreprise permet de réduire les coûts de certificat. Si votre organisation en a déployé une, les certificats des serveurs Edge internes doivent être émis par cette autorité de certification. L’utilisation d’une autorité de certification interne à l’entreprise permet de réduire les coûts de certificat.

Pour obtenir la liste des certificats requis pour les composants de serveurs Edge, reportez-vous à [Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md). Pour plus d’informations sur l’obtention de certificats auprès d’une autorité de certification publique, reportez-vous à [Demande des certificats pour les composants Edge dans Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md). Pour plus d’informations sur la demande, l’installation et l’affectation de certificats, reportez-vous à [Configuration des certificats de serveur Edge pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).

