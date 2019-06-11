---
title: Liste de vérification de déploiement de Lync Server 2013 pour les conférences Web
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5f845fd57846d7f9b58351d1cb77f3f1c0142ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Liste de vérification de déploiement pour les conférences Web dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-30_

Comme pour le déploiement de vos autres composants Lync Server 2013, le déploiement de conférences Web nécessite l’utilisation du générateur de topologie pour créer et publier une topologie incluant des conférences.

<div>

## <a name="deployment-sequence"></a>Séquence de déploiement

Vous pouvez déployer des conférences en même temps que le déploiement de votre topologie initiale ou après le déploiement d’au moins un pool frontal ou d’un serveur Standard Edition Server.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Processus de déploiement de conférences

Le tableau suivant fournit une vue d’ensemble des étapes nécessaires au déploiement des conférences dans une topologie existante.


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
<th>Rôles et appartenance aux groupes</th>
<th>Documentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installer le matériel et les logiciels prérequis</strong></p></td>
<td><p>Les conférences s’exécutent sur des serveurs frontaux dans un pool frontal ou un serveur Standard Edition Server. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.</p>
<div>

> [!NOTE]  
> Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint. Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, reportez-vous à la rubrique <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configuration de l’intégration avec Office Web Apps Server et Lync Server 2013</A>.


</div></td>
<td><p>Utilisateur du domaine qui est membre du groupe Administrateurs local</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel compatible pour Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Support du logiciel serveur et de l’infrastructure dans Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Déterminez la configuration système requise pour Lync Server 2013</a> dans la documentation de planification.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
<tr class="even">
<td><p><strong>Création de la topologie interne appropriée pour prendre en charge la conférence</strong></p></td>
<td><p>Exécutez le générateur de topologie pour ajouter des conférences à la topologie, puis publiez la topologie.</p></td>
<td><p>Pour définir une topologie, un compte membre du groupe Utilisateurs local</p>
<p>Pour publier la topologie, un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers 2013 Lync Server (de façon à ce que le générateur de topologie puisse configurer les DACL requis)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Définissez et configurez une topologie dans le générateur de topologies de Lync Server 2013</a> dans la documentation de déploiement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configuration des stratégies de conférence et de la prise en charge</strong></p></td>
<td><p>Utilisez le panneau de configuration de Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de conférence.</p></td>
<td><p>Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affecter des utilisateurs au rôle [] ou CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Stratégies de conférence dans Lync Server 2013</a> dans la documentation opérations.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 inclut désormais le paramètre **MaxUploadFileSizeMb** , qui limite la taille des fichiers qui peuvent être téléchargés pendant une réunion. La valeur par défaut de ce paramètre est 500 Mo. Vous pouvez ajuster **MaxUploadFileSizeMb** à l’aide de l’applet **de passe Set-CsConferencingConfiguration** .

**MaxUploadFileSizeMb** ne limite pas le paramètre de chargement de fichier de Lync Web App. La limite de chargement de taille de fichier pour Lync Web App est définie sur environ 30 Mo et est contrôlée par le fichier Web.\[config\]IIS:/DataCollabWeb/int ext/Handler/Web.config. Pour configurer la limite de chargement de taille de fichier pour Lync Web `maxRequestLength` App `maxAllowedContentLength` , mettez à jour et dans le fichier Web. config, comme illustré ci-dessous.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Vous devez mettre à jour le fichier Web. config pour chaque serveur frontal.

</div>

</div>

<span> </span>

</div>

</div>

</div>

