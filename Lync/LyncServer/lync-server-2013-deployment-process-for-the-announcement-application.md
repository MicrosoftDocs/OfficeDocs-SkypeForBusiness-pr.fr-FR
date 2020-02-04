---
title: 'Lync Server 2013 : processus de déploiement de l’application annonce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Processus de déploiement de l’application d’annonce dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-12_

Cette section fournit une vue d’ensemble des étapes de déploiement de l’application d’annonce. Vous devez déployer Enterprise Voice avant de configurer les annonces. Les composants requis par l’application d’annonce sont installés et activés lorsque vous déployez Enterprise Voice.

### <a name="announcement-deployment-process"></a>Procédure de déploiement des annonces

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Rôles</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurer les paramètres d’annonce</p></td>
<td><ul>
<li><p>Créez l’annonce en enregistrant et en téléchargeant des fichiers audio ou en utilisant la synthèse vocale (TTS).</p></li>
<li><p>Configurez les plages de numéros non attribués dans la table des numéros non attribués et associez-les à l’annonce appropriée.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Créer une annonce dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configuration de la table des numéros non attribués dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vérifier le déploiement de votre annonce</p></td>
<td><p>Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">Facultatif Vérifier le déploiement d’annonce dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

