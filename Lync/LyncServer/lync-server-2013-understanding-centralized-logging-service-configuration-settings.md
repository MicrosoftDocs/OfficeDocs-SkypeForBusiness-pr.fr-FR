---
title: "Présentation des param. de config. du service de journalisation centralisée"
TOCtitle: "Présentation des param. de config. du service de journalisation centralisée"
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49891312
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Présentation des paramètres de configuration du service de journalisation centralisée

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le service de journalisation centralisée est configuré pour définir les éléments qu’il est appelé à collecter, le mode de collecte, la source de collecte, ainsi que les paramètres de journalisation. Ces paramètres sont définis à une échelle globale (c’est-à-dire, pour le déploiement entier) ou au niveau d’un site (c’est-à-dire, un site déterminé dans votre déploiement). La journalisation que vous définissez utilise les paramètres appropriés à l’identité utilisée pour les commandes de démarrage, d’arrêt, de vidage et de recherche de journaux.

## Pour afficher la configuration active du service de journalisation centralisée

Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

Tapez ce qui suit dans une invite de ligne de commande :

    Get-CsClsConfiguration

> [!TIP]  
> Vous pouvez limiter ou étendre la portée des paramètres de configuration retournés en définissant <code>-Identity</code> et une portée (par exemple, « Site:Redmond » pour retourner uniquement CsClsConfiguration pour le site Redmond. Si vous avez besoin de détails sur une partie spécifique de la configuration, vous pouvez rediriger le résultat vers une autre applet de commande Windows PowerShell. Par exemple, pour obtenir des détails sur les scénarios définis dans la configuration du site « Redmond », tapez : <code>Get-CsClsConfiguration -Identity &quot;site:Redmond&quot; | Select-Object -ExpandPropery Scenarios</code>

![Exemple de sortie de Get-CsClsConfiguration.](images/JJ688138.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemple de sortie de Get-CsClsConfiguration.")

Le résultat de l’applet de commande affiche la configuration active du service de journalisation centralisée.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre de configuration</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identity</strong></p></td>
<td><p>Identifie la portée et le nom de cette configuration. Il existe une seule configuration globale et une seule configuration par site.</p></td>
</tr>
<tr class="even">
<td><p><strong>Scenarios</strong></p></td>
<td><p>Liste de tous scénarios définis pour cette configuration.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SearchTerms</strong></p></td>
<td><p>Termes de recherche définis pour la configuration. Office 365, pas de déploiements locaux.</p></td>
</tr>
<tr class="even">
<td><p><strong>SecurityGroups</strong></p></td>
<td><p>Groupes de sécurité définis déterminant les personnes (c’est-à-dire, les membres des groupes de sécurité) autorisées à voir les ordinateurs du sur lequel elles se trouvent. Dans ce contexte, il s’agit du site défini dans le Générateur de topologie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Regions</strong></p></td>
<td><p>Les régions définies servent à collecter les groupes de sécurité (SecurityGroups) dans une région, par exemple, EMEA (Europe/Moyen-Orient/Afrique).</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileFolder</strong></p></td>
<td><p>Chemin d’accès défini à l’emplacement où sont écrits les fichiers journaux sur les ordinateurs. CLSAgent écrit les fichiers journaux et s’exécute dans le contexte du service réseau. Dans ce cas, %TEMP% s’étend vers %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
<td><p>Ce paramètre indique la taille maximale du fichier journal au-delà de laquelle un nouveau fichier journal de suivi d’événements (.etl) est créé. Un nouveau fichier journal est créé quand la taille définie est atteinte, même si la durée maximale définie dans EtlFileRolloverMinutes n’a pas encore été atteinte.</p></td>
</tr>
<tr class="even">
<td><p><strong>EtlFileRolloverMinutes</strong></p></td>
<td><p>Durée maximale définie en minutes au-delà de laquelle un nouveau fichier .etl est créé. Un nouveau fichier local est créé quand le minuteur arrive à expiration, même si la taille maximale définie dans EtlFileRolloverSizeMB n’a pas encore été atteinte.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TmfFileSearchPath</strong></p></td>
<td><p>Emplacement dans lequel rechercher les fichiers au format de message de suivi. Les fichiers au format de message de suivi servent à convertir les fichiers binaires en format lisible.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalFolders</strong></p></td>
<td><p>Chemin d’accès défini à l’emplacement où sont écrits les fichiers cache sur les ordinateurs. CLSAgent écrit les fichiers cache et s’exécute dans le contexte du service réseau. Dans ce cas, %TEMP% s’étend vers %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Par défaut, les fichiers cache et les fichiers journaux sont écrits dans le même répertoire.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileNetworkFolder</strong></p></td>
<td><p>Vous pouvez définir un chemin d’accès UNC (Universal Naming Convention) pour recevoir les fichiers cache lors des opérations de journalisation.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
<td><p>Définit la durée maximale de conservation des fichiers cache, en jours.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
<td><p>Définit le pourcentage d’espace disque pouvant être utilisé par les fichiers cache.</p></td>
</tr>
<tr class="even">
<td><p><strong>ComponentThrottleLimit</strong></p></td>
<td><p>Définit le nombre maximal de traces par seconde pouvant être créées par un composant avant le déclenchement du limiteur automatique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ComponentThrottleSample</strong></p></td>
<td><p>Nombre de fois que la limite ComponentThrottleLimit peut être dépassée en l’espace de 60 secondes.</p></td>
</tr>
<tr class="even">
<td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
<td><p>Version minimale de CLSAgent autorisée à s’exécuter. Cet élément est prévu pour Office 365.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[Présentation du service de journalisation centralisée](lync-server-2013-overview-of-the-centralized-logging-service.md)  

#### Autres ressources

[Set-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClsConfiguration)  
[Remove-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsClsConfiguration)  
[New-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClsConfiguration)  
[Get-CsClsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsClsConfiguration)

