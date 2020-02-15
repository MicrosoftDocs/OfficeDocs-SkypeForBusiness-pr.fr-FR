---
title: 'Lync Server 2013 : demande des certificats à l’avance (facultatif)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c2df4d328154133df91503877a22234e6a05aa3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Demander des certificats à l’avance (facultatif) pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Les certificats sont requis pour tous les serveurs internes qui exécutent Lync Server 2013, y compris chaque serveur frontal Enterprise Edition, Standard Edition Server, directeur, serveur Edge et serveur de médiation autonome. Bien qu’il soit recommandé d’utiliser une autorité de certification d’entreprise interne pour les serveurs internes, vous pouvez également utiliser une autorité de certification publique. Pour plus d’informations sur les exigences de certificat et sur l’utilisation d’une autorité de certification publique, voir [Certificate Requirements for Internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.

Le programme d’installation de Lync Server 2013 inclut l’Assistant certificat, qui facilite les tâches de demande, d’affectation et d’installation de certificats pendant le déploiement. Si vous souhaitez demander des certificats avant d’installer les serveurs (par exemple, pour gagner du temps pendant le déploiement effectif des serveurs), vous pouvez utiliser un ordinateur sur lequel les outils d’administration Lync Server 2013 sont installés ou à l’aide d’une demande de certificat. procédure définie dans votre organisation, à condition que vous vous assurez que les certificats sont exportables et qu’ils contiennent tous les autres noms de sujet requis. Demander des certificats à l’avance est facultatif. Si vous ne les demandez pas à l’avance, vous devez les demander dans le cadre de la configuration de chaque serveur nécessitant un certificat.

Cette documentation de déploiement fournit des procédures pour l’utilisation de l’Assistant Certificat pour demander des certificats dans le cadre du processus de configuration, comme décrit dans la section configurer des certificats pour les serveurs de Lync [server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurer des certificats pour le directeur dans Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)et [installer les fichiers pour le serveur de médiation dans les sections Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) de la documentation de déploiement. Si vous demandez des certificats à l’avance, vous devez modifier les procédures de déploiement de certificat de ces sections de manière à pouvoir importer et attribuer les certificats au lieu de les demander au moment du déploiement.

<div>


> [!NOTE]  
> Lync Server 2013 inclut la prise en charge des certificats SHA-256 pour les connexions provenant de clients exécutant les&nbsp;systèmes d’exploitation Windows&nbsp;Vista&nbsp;, windows Server 2008, Windows Server 2008 R2 et Windows 7, ainsi que Lync Phone Edition. Pour permettre la prise en charge de l’accès externe via SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.



</div>

</div>

<span> </span>

</div>

</div>

</div>

