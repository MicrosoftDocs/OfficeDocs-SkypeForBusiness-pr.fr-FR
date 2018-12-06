---
title: 'Lync Server 2013 : Demande des certificats à l’avance (facultatif)'
TOCTitle: Demande des certificats à l’avance (facultatif)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412733(v=OCS.15)
ms:contentKeyID: 49298324
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Demande des certificats à l’avance (facultatif) pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Des certificats sont requis pour tous les serveurs internes qui exécutent Lync Server 2013, y compris chaque serveur frontalEnterprise Edition, serveur Standard Edition, directeur, serveur Edge et serveur de médiation autonome. Même s’il est recommandé d’utiliser une autorité de certification d’entreprise interne pour les serveurs internes, vous pouvez également utiliser une autorité de certification publique. Pour plus d’informations sur les certificats requis et l’utilisation d’une autorité de certification publique, reportez-vous à [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.

L’installation de Lync Server 2013 inclut l’Assistant Certificat, qui simplifie les opérations de demande, d’attribution et d’installation de certificats pendant le déploiement. Si vous souhaitez demander des certificats avant d’installer des serveurs (par exemple, pour gagner du temps lors de leur déploiement réel), vous pouvez le faire à l’aide d’un ordinateur sur lequel les outils d’administration de Lync Server 2013 sont installés ou en utilisant une procédure de demande de certificat définie dans votre organisation, dans la mesure où les certificats sont exportables et contiennent tous les autres noms du sujet requis. Demander des certificats à l’avance est facultatif ; si vous ne le faites pas, vous devez les demander dans le cadre de l’installation de chaque serveur nécessitant un certificat.

Cette documentation de déploiement fournit les procédures d’utilisation de l’Assistant Certificat pour demander des certificats dans le cadre du processus d’installation, conformément à la description des sections [Configuration des certificats pour les serveurs dans Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configuration des certificats pour le directeur dans Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) et [Installation des fichiers du serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) de cette documentation de déploiement. Si vous demandez des certificats à l’avance, vous devez modifier les procédures de déploiement de certificat de ces sections de manière à pouvoir importer et attribuer les certificats au lieu de les demander au moment du déploiement.

> [!NOTE]  
> Lync Server 2013 inclut la prise en charge des certificats SHA-256 pour les connexions à partir de clients exécutant les systèmes d’exploitation Windows Vista, Windows Server 2008, Windows Server 2008 R2, Windows 7 et Lync Phone Edition. Pour permettre la prise en charge de l’accès externe via SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.
