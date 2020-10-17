---
title: Liste de vérification du déploiement de Lync Server 2013 pour les conférences Web
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c20bd593e11f032ba0a0ed852a50b6d417fa604
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531091"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Liste de vérification du déploiement pour la conférence Web dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-30_

Comme avec le déploiement de vos autres composants Lync Server 2013, le déploiement de la conférence Web nécessite que vous utilisiez le générateur de topologie pour créer et publier une topologie qui incorpore la Conférence.

<div>

## <a name="deployment-sequence"></a>Séquence de déploiement

Vous pouvez déployer la Conférence en même temps que vous déployez votre topologie initiale ou après avoir déployé au moins un pool frontal ou un serveur Standard Edition.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Processus de déploiement de la conférence

Le tableau suivant décrit les étapes nécessaires pour déployer la conférence dans une topologie existante.


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
<td><p>La Conférence s’exécute sur les serveurs frontaux d’un pool frontal et de serveurs Standard Edition. Aucune configuration matérielle ou logicielle supplémentaire n’est requise en dehors de celle nécessaire à l’installation de ces serveurs.</p>
<div>

> [!NOTE]  
> Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint. Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, voir Configuration de l' <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">intégration à Office Web Apps Server et Lync Server 2013</A>.


</div></td>
<td><p>Utilisateur du domaine qui est membre du groupe Administrateurs local</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge du logiciel et de l’infrastructure serveur dans Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a> dans la documentation de planification.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
<tr class="even">
<td><p><strong>Créer la topologie interne appropriée pour prendre en charge la conférence</strong></p></td>
<td><p>Exécutez le générateur de topologie pour ajouter la Conférence à la topologie, puis publiez la topologie.</p></td>
<td><p>Pour définir une topologie, un compte membre du groupe Utilisateurs local</p>
<p>Pour publier la topologie, un compte membre du groupe administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers Lync Server 2013 (afin que le générateur de topologies puisse configurer les DACL requises)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Définissez et configurez une topologie dans le générateur de topologies pour Lync Server 2013</a> dans la documentation de déploiement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurer la prise en charge et les stratégies de conférence</strong></p></td>
<td><p>Utilisez le panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de conférence.</p></td>
<td><p>Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle [] ou CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Stratégies de conférence dans Lync Server 2013</a> dans la documentation des opérations.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 inclut désormais le paramètre **MaxUploadFileSizeMb** , qui limite la taille des fichiers pouvant être chargés pendant une réunion. La valeur par défaut de ce paramètre est de 500 Mo. Vous pouvez ajuster **MaxUploadFileSizeMb** à l’aide de la cmdlet **Set-CsConferencingConfiguration** .

**MaxUploadFileSizeMb** ne limite pas le paramètre de téléchargement de fichiers pour Lync Web App. La limite de téléchargement de taille de fichier pour Lync Web App est définie sur environ 30 Mo et est contrôlée par le fichier IIS web.config:/DataCollabWeb/Int \[ ext \] /handler/web.config. Pour configurer la limite de chargement de taille de fichier pour Lync Web App, mettez à jour `maxRequestLength` et `maxAllowedContentLength` dans le fichier web.config, comme indiqué ci-dessous.

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

Vous devez mettre à jour le fichier web.config pour chaque serveur frontal.

</div>

</div>

<span> </span>

</div>

</div>

</div>

