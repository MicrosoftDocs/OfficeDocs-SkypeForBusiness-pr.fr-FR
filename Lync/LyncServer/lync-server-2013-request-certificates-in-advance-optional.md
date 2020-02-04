---
title: 'Lync Server 2013 : Demande des certificats à l’avance (facultatif)'
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
ms.openlocfilehash: 7ee4598f35bb607a9262bfeb7931e2c88e27920c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>Demande des certificats à l’avance (facultatif) pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Des certificats sont requis pour tous les serveurs internes exécutant Lync Server 2013, y compris chaque serveur principal Enterprise Edition, Standard Edition Server, directeur, serveur Edge et serveur de médiation autonome. Même si une autorité de certification d’entreprise interne est recommandée pour les serveurs internes, vous pouvez également utiliser une autorité de certification publique. Pour plus d’informations sur les exigences relatives aux certificats et sur l’utilisation d’une autorité de certification publique, voir la [Configuration requise pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.

Le programme d’installation de Lync Server 2013 inclut l’Assistant certificat, qui facilite la tâche de demande, d’attribution et d’installation de certificats lors du déploiement. Si vous souhaitez demander des certificats avant d’installer des serveurs (par exemple, pour gagner du temps au cours du déploiement réel des serveurs), vous pouvez le faire à l’aide d’un ordinateur sur lequel sont installés les outils d’administration de Lync Server 2013 ou à l’aide d’une demande de certificat. procédure définie au sein de votre organisation, tant que vous vous assurez que les certificats sont exportables et contiennent tous les noms d’objet alternatifs requis. La demande de certificats à l’avance est facultative. Dans le cas contraire, vous devez les demander dans le cadre de l’installation de chaque serveur nécessitant un certificat.

Cette documentation de déploiement fournit des procédures d’utilisation de l’Assistant Certificat pour demander des certificats dans le cadre du processus d’installation, comme décrit dans la rubrique [configurer des certificats pour les serveurs dans Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [configurer des certificats pour le directeur dans Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)et [installer les fichiers pour le serveur de médiation dans les sections Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) de cette documentation de déploiement. Si vous demandez des certificats à l’avance, vous devez modifier les procédures de déploiement des certificats dans ces sections selon les besoins en matière d’importation et d’attribution de certificats au lieu de les demander au moment du déploiement.

<div>


> [!NOTE]  
> Lync Server 2013 inclut la prise en charge des certificats SHA-256 pour les connexions de clients exécutant les systèmes&nbsp;d’exploitation Windows Vista&nbsp;,&nbsp;windows Server 2008, Windows Server 2008 R2 et Windows 7 et Lync Phone Edition. Pour prendre en charge l’accès externe à l’aide de l’algorithme SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.



</div>

</div>

<span> </span>

</div>

</div>

</div>

