---
title: "Liste de vérif. du déploiement pour la conférence web dans Lync Server 2013"
TOCtitle: "Liste de vérif. du déploiement pour la conférence web dans Lync Server 2013"
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205104(v=OCS.15)
ms:contentKeyID: 49298250
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de vérification du déploiement pour la conférence web dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Comme avec le déploiement de vos autres composants Lync Server 2013, le déploiement de la conférence web nécessite l’utilisation du Générateur de topologie pour créer et publier une topologie qui incorpore la conférence.

## Séquence de déploiement

Vous pouvez déployer la conférence en même temps que la topologie initiale ou après avoir déployé au moins un pool de serveurs frontaux ou un serveur Standard Edition.

## Processus de déploiement de la conférence

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
<td><p>La conférence s’exécute sur des serveurs frontaux dans un pool de serveurs frontaux et un serveurs Standard Edition. Elle ne présente aucune exigence matérielle ou logicielle supplémentaire au-delà de celles requises pour installer ces serveurs.</p>

> [!NOTE]  
> Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et l’affichage des présentations PowerPoint. Pour plus d’informations sur l’installation et la configuration de Office Web Apps Server, voir <a href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuration de l’intégration à Office Web Apps Server et Lync Server 2013</a>.

</td>
<td><p>Utilisateur du domaine qui est membre du groupe Administrateurs local</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013</a> dans la documentation de prise en charge.</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a> dans la documentation de planification.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Créer la topologie interne appropriée pour prendre en charge la conférence</strong></p></td>
<td><p>Exécutez le Générateur de topologie pour ajouter la conférence à la topologie, puis publiez la topologie.</p></td>
<td><p>Pour définir une topologie, un compte membre du groupe Utilisateurs local</p>
<p>Pour publier la topologie, un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle complètes (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers de Lync Server 2013 (afin que le Générateur de topologie puisse configurer les listes DACL requises)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Définition et configuration d’une topologie dans le générateur de topologie pour Lync Server 2013</a> dans la documentation de déploiement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurer la prise en charge et les stratégies de conférence</strong></p></td>
<td><p>Utilisez le Panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de conférence.</p></td>
<td><p>Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affectez des utilisateurs au rôle [] ou CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Stratégies de conférence dans Lync Server 2013</a> dans la documentation des opérations.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 inclut désormais le paramètre **MaxUploadFileSizeMb**, qui limite la taille des fichiers pouvant être téléchargés durant une réunion. La valeur par défaut de ce paramètre est 500 Mo. Vous pouvez ajuster **MaxUploadFileSizeMb** à l’aide de l’applet de commande **Set-CsConferencingConfiguration**.

**MaxUploadFileSizeMb** ne limite pas le paramètre de téléchargement de fichier pour Lync Web App. La taille limite de téléchargement de fichier pour Lync Web App est définie à environ 30 Mo et contrôlée par le fichier web.config IIS : /DataCollabWeb/Int\[Ext\]/Handler/web.config. Pour configurer la taille limite de téléchargement de fichier pour Lync Web App, mettez à jour `maxRequestLength` et `maxAllowedContentLength` dans le fichier web.config comme indiqué ci-dessous.

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

