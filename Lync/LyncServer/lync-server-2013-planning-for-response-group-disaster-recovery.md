---
title: "Lync Server 2013 : Plan. de la récup. d’urgence des groupes Response Group"
TOCTitle: Planification de la récupération d’urgence des groupes Response Group
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204699(v=OCS.15)
ms:contentKeyID: 49296345
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de la récupération d’urgence des groupes Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section explique comment préparer la récupération d’urgence des groupes Response Group et présente le processus de récupération d’urgence.

## Préparation à la récupération d’urgence du Response Group

Gardez les points suivants à l’esprit lorsque vous préparez et réalisez des procédures de récupération d’urgence.

> [!NOTE]  
> Dans un environnement de coexistence, seuls les groupes Response Group de Lync Server 2013 sont pris en charge pour les procédures de récupération d’urgence décrites dans ce document.

  - Planifiez la récupération d’urgence lorsque vous effectuez votre planification de capacité. Pour la capacité de la récupération d’urgence, chaque pool d’un pool jumelé doit être capable de gérer les charges de travail de tous les groupes Response Group dans les deux pools. Pour en savoir plus sur la planification de capacité de Response Group, reportez-vous à [Planification de capacité de Response Group dans Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - Effectuez des copies de sauvegarde régulières de toutes les configurations des groupes Response Group dans tous les pools de serveurs frontaux dans lesquels vous avez déployé l’application Response Group en suivant la procédure d’exportation décrite dans ce document. Pour plus d’informations, reportez-vous à [Procédures de récupération d’urgence des groupes Response Group dans Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Conservez les copies de sauvegarde en lieu sûr.

  - Conservez une copie de sauvegarde distincte de tous les fichiers audio d’origine que vous avez utilisés pour l’application Response Group, dont les enregistrements et les fichiers de mise en attente musicale. Conservez les fichiers de sauvegarde en lieu sûr.

  - Pour la récupération d’urgence de Lync Server 2013, tous les paramètres Response Group doivent comporter des noms uniques dans tout votre déploiement. Cette exigence s’applique aux flux de travail, files d’attente, groupes d’agents, groupes de congés et heures ouvrées. Vous devez vérifier que cette exigence est remplie alors que le pool principal et le pool de sauvegarde sont encore actifs et avant de devoir initier la procédure de basculement. Si vous rencontrez des conflits de noms lors de l’importation des données Response Group dans le pool de sauvegarde, l’importation échoue. Pour réaliser l’importation et la procédure de basculement, vous devez résoudre les conflits de noms en renommant l’objet Response Group dans le pool de sauvegarde ou en utilisant l’applet de commande **Import-CsRgsConfiguration** avec le paramètre –ResolveNameConflicts pour résoudre automatiquement le conflit en ajoutant un numéro unique d’identification à l’objet Response Group.

  - En règle générale, nous vous recommandons d’effectuer des sauvegardes quotidiennes, mais si le volume de vos changements est élevé, vous pouvez planifier des sauvegardes plus fréquentes. La quantité d’informations que vous risquez de perdre en cas d’incident dépend de la fréquence de vos sauvegardes, ainsi que de la fréquence et du volume des changements.

  - Il est possible d’importer des groupes Response Group dans un pool de sauvegarde avant qu’un incident ou qu’une opération de basculement ne se produise. L’importation des groupes Response Group en avance réduit le temps mort, car le service Response Group Lync Server peut être restauré dans le pool de sauvegarde dès que les appels sont routés vers le pool de sauvegarde.
    
    > [!NOTE]  
    > L’application Response Group ne peut pas atteindre les agents hébergés dans un pool inactif tant que le basculement n’est pas terminé. Pendant ce temps, les processus de l’application Response Group appellent comme si ces agents étaient indisponibles.

## Processus de récupération d’urgence de Response Group

En cas d’incident, vous pouvez récupérer les groupes Response Group en suivant l’une des approches suivantes :

  - Basculez sur un pool de sauvegarde, puis rebasculez sur le pool d’origine.

  - Basculez sur un pool de sauvegarde, créez un nouveau pool avec un nom de domaine complet (FQDN) différent, puis importez les groupes Response Group dans le nouveau pool.

Au cours de la phase de basculement de la récupération d’urgence, les groupes Response Group se trouvent dans plusieurs pools : dans le pool principal (qui est indisponible) et dans le pool de sauvegarde. Les groupes Response Group dans les deux pools portent le même nom et ont le même propriétaire (le pool principal), mais ils ont des parents différents.

Lorsque vous effectuez la récupération en créant un nouveau pool avec un nom de domaine complet FQDN différent, vous devez affecter le nouveau pool comme propriétaire des groupes Response Group lorsque vous les importez. La propriété des groupes Response Group demeure avec le pool d’origine jusqu’à ce que vous réaffectiez explicitement la propriété à l’aide du paramètre –OverwriteOwner avec l’applet de commande **Import-CsRgsConfiguration**.

> [!NOTE]  
> Vous devez également utiliser le paramètre –OverwriteOwner si vous avez recréé le pool au cours de la récupération (c’est-à-dire si la base de données Response Group est vide), que vous utilisiez ou non le même nom de domaine complet FQDN. Vous n’avez pas besoin d’utiliser le paramètre –OverwriteOwner si vous n’avez pas créé le pool, mais il est permis d’utiliser ce paramètre lorsque vous réimportez les groupes Response Group dans le pool principal.

Vous ne pouvez définir qu’un seul ensemble de paramètres de configuration Response Group de niveau application par pool. Ces paramètres incluent la configuration de la mise en attente musicale par défaut, le fichier audio de mise en attente musicale par défaut, la période de grâce de reprise d’appel parqué de l’agent et la configuration du contexte de l’appel. Pour afficher ces paramètres de configuration, exécutez l’applet de commande **Get-CsRgsConfiguration**. Pour plus d’informations sur l’applet de commande **Get-CsRgsConfiguration**, reportez-vous à [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

Vous pouvez transférer ces paramètres de niveau application d’un pool à un autre à l’aide de l’applet de commande **Import-CsRgsConfiguration** avec le paramètre –ReplaceExistingSettings, mais cette opération remplace les paramètres du pool de destination.

> [!IMPORTANT]  
> Cette contrainte concernant le transfert des paramètres vers un autre pool est vraie uniquement pour les paramètres de niveau application et pour le fichier audio de mise en attente musicale par défaut. Elle ne s’applique pas aux groupes d’agents, aux files d’attente, aux flux de travail, aux heures ouvrées ni aux groupes de congés.

Si vous ne souhaitez pas remplacer les paramètres de niveau application dans le pool de sauvegarde en cas d’incident et que le pool principal ne peut pas être récupéré, les paramètres de niveau application du pool principal seront perdus. Si vous devez créer un nouveau pool pour remplacer le pool principal au cours de la récupération, soit avec le même nom de domaine complet FQDN, soit avec un nom de domaine complet FQDN différent, vous ne pouvez pas récupérer les paramètres de niveau application d’origine. Dans ce cas, vous devez configurer le nouveau pool avec ces paramètres et inclure le fichier audio de mise en attente musicale.

Si vous décidez d’utiliser l’applet de commande **Import-CsRgsConfiguration** pour transférer les paramètres de niveau application du pool principal vers le pool de sauvegarde en cas d’incident, vous pouvez dans ce cas transférer les paramètres du pool de sauvegarde vers le nouveau pool au cours de la récupération de la même manière que vous les avez transférés du pool principal vers le pool de sauvegarde.

Le tableau ci-dessous présente les étapes requises pour récupérer les groupes Response Group.

Pour plus d’informations sur l’exécution de ces étapes, reportez-vous à [Procédures de récupération d’urgence des groupes Response Group dans Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### Étapes de récupération d’urgence de Response Group

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Groupes et rôles requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Avant une panne</p></td>
<td><p>De manière régulière, exécutez l’applet de commande <strong>Export-CsRgsConfiguration</strong> pour créer des sauvegardes de toutes les configurations Response Group dans tous les pools de serveurs frontaux où l’application Response Group est déployée.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Pendant une panne</p></td>
<td><p>Exécutez l’applet de commande <strong>Import-CsRgsConfiguration</strong> pour importer la configuration du service Response Group Lync Server sauvegardée du pool principal vers le pool de sauvegarde.</p>
<div>

> [!NOTE]  
> Utilisez le paramètre –ReplaceExistingSettings pour remplacer les paramètres Response Group de niveau application dans le pool de sauvegarde par les paramètres du pool principal. Si vous ne transférez pas les paramètres de niveau application du pool principal vers le pool de sauvegarde, et si le pool principal ne peut pas être récupéré, vous perdrez les paramètres du pool principal.
</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Après l’importation</p></td>
<td><p>Exécutez l’applet de commande Response Group avec le paramètre –ShowAll (pour afficher tous les groupes Response Group) ou avec le paramètre –Owner (pour afficher uniquement les groupes Response Group importés) afin de vérifier que toutes les configurations Response Group ont été importées dans le pool de sauvegarde.</p>
<div>

> [!IMPORTANT]  
> Si vous n’utilisez ni le paramètre –ShowAll, ni le paramètre –Owner, les groupes Response Group que vous avez importés dans le pool de sauvegarde ne seront pas répertoriés dans les résultats renvoyés par les applets de commande.
</div>
<p>Exécutez les applets de commande suivantes :</p><ul><li><p><strong>Get-CsRgsWorkflow</strong></p></li><li><p><strong>Get-CsRgsQueue</strong></p></li><li><p><strong>Get-CsRgsAgentGroup</strong></p></li><li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li><li><p><strong>Get-CsRgsHolidaySet</strong></p></li></ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Après un basculement</p></td>
<td><ul><li><p>Effectuez un test d’appel vers un groupe Response Group qui a été importé dans le pool de sauvegarde et vérifiez que l’appel est géré correctement.</p></li><li><p>Tous les agents formels doivent se reconnecter à leurs groupes formels dans le pool de sauvegarde.</p></li><li><p>Gérer les changements de configuration :</p>
<p>Les groupes Response Group dans le pool de sauvegarde, qu’ils soient importés dans le pool de sauvegarde ou qu’ils soient la propriété du pool de sauvegarde, peuvent être modifiés comme d’habitude pendant la panne.</p>
<div>

> [!IMPORTANT]  
> Vous devez utiliser Lync Server Management Shell pour gérer les groupes Response Group que vous avez importés dans le pool de sauvegarde. Vous ne pouvez pas utiliser Panneau de configuration Lync Server pour gérer ces groupes Response Group lorsqu’ils se trouvent dans le pool de sauvegarde.
</div></li></ul></td>
<td><p>N/A</p></td>
</tr>
<tr class="odd">
<td><p>Après une récupération, avant une restauration</p></td>
<td><p>Exécutez l’applet de commande <strong>Export-CsRgsConfiguration</strong> en spécifiant le paramètre -Source comme pool de sauvegarde et le paramètre –Owner comme pool principal pour exporter les groupes Response Group détenus par le pool principal à partir du pool de sauvegarde.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Après une restauration</p></td>
<td><ul><li><p>Exécutez l’applet de commande <strong>Import-CsRgsConfiguration</strong> pour réimporter les groupes Response Group dans le pool principal.</p>
<div>

> [!NOTE]  
> Si le pool principal ne peut pas être récupéré et que vous déployez un nouveau pool pour le remplacer, utilisez le paramètre –ReplaceExistingSettings pour transférer les paramètres de niveau application du pool de sauvegarde vers le nouveau pool. Si vous ne souhaitez pas transférer les paramètres du pool de sauvegarde, le nouveau pool utilisera les paramètres par défaut.
</div></li><li><p>Exécutez les applets de commande suivantes avec le paramètre –ShowAll (pour afficher tous les groupes Response Group) ou avec le paramètre –Owner (pour afficher uniquement les groupes Response Group importés) afin de vérifier que toutes les configurations Response Group ont été réimportées dans le pool principal :</p><ul><li><p><strong>Get-CsRgsWorkflow</strong></p></li><li><p><strong>Get-CsRgsQueue</strong></p></li><li><p><strong>Get-CsRgsAgentGroup</strong></p></li><li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li><li><p><strong>Get-CsRgsHolidaySet</strong></p></li></ul></li><li><p>Effectuez un test d’appel vers un groupe Response Group qui a été réimporté dans le pool principal et vérifiez que l’appel est géré correctement.</p></li><li><p>Vous pouvez également exécuter l’applet de commande <strong>Export-CsRgsConfiguration</strong> dans le pool de sauvegarde avec le paramètre –RemoveExportedConfiguration pour supprimer du pool de sauvegarde les groupes Response Group détenus par le pool principal.</p></li></ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>

