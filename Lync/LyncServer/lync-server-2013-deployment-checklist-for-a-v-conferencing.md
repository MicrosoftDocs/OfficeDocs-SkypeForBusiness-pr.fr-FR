---
title: "Liste de vérif. du déploiement pour la conférence A/V dans Lync Server 2013"
TOCtitle: "Liste de vérif. du déploiement pour la conférence A/V dans Lync Server 2013"
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49297551
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste de vérification du déploiement pour la conférence A/V dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

À l’instar du déploiement de vos autres composants Lync Server 2013, le déploiement de la conférence A/V requiert que vous utilisiez le Générateur de topologie pour créer et publier une topologie qui intègre la conférence.

## Séquence de déploiement

Vous pouvez déployer la conférence en même temps que la topologie initiale ou après que vous avez déployé au moins un pool de serveurs frontaux ou un serveur Standard Edition.

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
<td><p>La conférence s’exécute sur les serveurs frontaux d’un pool de serveurs frontaux et sur les serveurs Standard Edition. Elle n’exige aucune configuration matérielle ou logicielle supplémentaire en dehors de celles requises pour installer ces serveurs.</p>

> [!NOTE]  
> Lync Server 2013 utilise Office Web Apps et Office Web Apps Server pour gérer le partage et le rendu des présentations PowerPoint. Pour plus d’informations sur l’installation et la configuration d’Office Web Apps Server, voir <a href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuration de l’intégration à Office Web Apps Server et Lync Server 2013</a>.

</td>
<td><p>Utilisateur du domaine qui est membre du groupe Administrateurs local</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Matériel pris en charge pour Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Prise en charge des infrastructures et des logiciels de serveur dans Lync Server 2013</a> dans la documentation de prise en charge</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Détermination de la configuration système requise pour Lync Server 2013</a> dans la documentation de planification</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Configuration technique requise pour l’archivage dans Lync Server 2013</a> dans la documentation de planification</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Créer la topologie interne appropriée pour prendre en charge la conférence</strong></p></td>
<td><p>Exécutez le Générateur de topologie pour ajouter la conférence à la topologie, puis publiez la topologie.</p></td>
<td><p>Pour définir une topologie, un compte membre du groupe Utilisateurs local</p>
<p>Pour publier la topologie, un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins et qui dispose des autorisations de contrôle total (lecture/écriture/modification) sur le partage de fichiers à utiliser pour le magasin de fichiers de Lync Server 2013 (afin que le Générateur de topologie puisse configurer les DACL requises)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Définition et configuration d’une topologie dans le générateur de topologie pour Lync Server 2013</a> dans la documentation de déploiement</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurer la prise en charge et les stratégies de conférence</strong></p></td>
<td><p>Utilisez le Panneau de configuration Lync Server 2013 ou Lync Server Management Shell pour configurer les paramètres de conférence.</p></td>
<td><p>Groupe RTCUniversalServerAdmins (Windows PowerShell uniquement) ou affecter des utilisateurs au rôle [] ou CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Stratégies de conférence dans Lync Server 2013</a> dans la documentation des opérations</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Autres ressources

[Vue d’ensemble des conférences dans Lync Server 2013](lync-server-2013-overview-of-conferencing.md)  
[Définition de la configuration requise pour les conférences dans Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

