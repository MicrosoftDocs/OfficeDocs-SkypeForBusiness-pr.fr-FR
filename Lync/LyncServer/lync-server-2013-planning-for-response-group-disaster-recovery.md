---
title: 'Lync Server 2013 : Planification de la récupération d’urgence des groupes Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70622364349eb83ecbc171cb3d5bf894ba03d3f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Planification de la récupération d’urgence des groupes Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Cette section décrit quelques méthodes permettant de préparer des groupes de réponse pour une reprise après sinistre et offre une vue d’ensemble du processus de reprise après sinistre.

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>Préparation de la reprise après sinistre de Response Group

Gardez les points suivants à l’esprit lorsque vous préparez et mettez en oeuvre des procédures de reprise après sinistre.

<div>


> [!NOTE]  
> Dans un environnement de coexistence, seuls les groupes de réponse Lync Server 2013 sont pris en charge pour les procédures de reprise après sinistre décrites dans ce document.



</div>

  - Prévoyez une reprise après sinistre lors de la planification de la capacité. Pour la capacité de reprise après sinistre, chaque pool dans un pool couplé doit être en mesure de gérer les charges de travail de tous les groupes de réponses dans les deux pools. Pour plus d’informations sur la planification de la capacité du groupe de réponse, voir [planification de la capacité pour le groupe réponse dans Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - Prenez des copies de sauvegarde régulières de toutes les configurations de Response Group dans tous les pools frontaux dans lesquels vous avez déployé l’application Response Group à l’aide de la procédure d’exportation décrite dans ce document. Pour plus d’informations, consultez [procédures de rétablissement de sinistre de Response Group dans Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Conservez les copies de sauvegarde dans un emplacement sûr.

  - Conservez une copie de sauvegarde séparée de tous les fichiers audio d’origine que vous avez utilisés pour l’application Response Group, y compris tous les enregistrements et fichiers musicaux en attente. Conservez les fichiers de sauvegarde dans un emplacement sûr.

  - Dans le cas d’une reprise après sinistre Lync Server 2013, tous les paramètres de groupe de réponse doivent avoir des noms uniques au sein de votre déploiement. Cette condition s’applique aux flux de travail, files d’attente, groupes d’agents, jours fériés et heures d’activité. Assurez-vous que cette obligation est remplie lorsque les pools principal et de sauvegarde sont toujours actifs et avant d’avoir besoin de démarrer une procédure de reprise. Si vous rencontrez des conflits de nom lorsque vous importez des données de groupe de réponse au pool de sauvegarde, l’importation échoue. Pour achever la procédure d’importation et de basculement, vous devez résoudre les conflits de noms en renommant l’objet Response Group dans le pool de sauvegarde ou en utilisant l’applet de passe **Import-CsRgsConfiguration** avec le paramètre-ResolveNameConflicts automatiquement. Résolvez le conflit en ajoutant un numéro d’identification unique à l’objet Response Group.

  - En règle générale, il est recommandé d’effectuer des sauvegardes journalières, mais si vous avez un volume élevé de modifications, vous souhaiterez peut-être planifier des sauvegardes plus fréquentes. La quantité d’informations que vous pouvez perdre en cas de sinistre dépend de la fréquence de vos sauvegardes, ainsi que de la fréquence et du volume des modifications.

  - Il est possible d’importer des groupes de réponses dans un pool de sauvegarde avant qu’une opération de secours ou de reprise ne se produise. L’importation de groupes de réponse à l’avance réduit les temps d’arrêt, car le service du groupe de réponse du serveur Lync peut être restauré dans le pool de sauvegarde dès que les appels sont routés vers le pool de sauvegarde.
    
    <div>
    

    > [!NOTE]  
    > L’application Response Group ne peut pas accéder aux agents hébergés dans un pool inactif jusqu’à ce que le basculement soit terminé. Pendant ce temps, l’application du groupe de réponse traite les appels comme s’ils ne sont pas disponibles.

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>Processus de récupération d’urgence de Response Group

Dans le cas d’un sinistre, vous pouvez récupérer des groupes de réponse en utilisant l’une des approches suivantes:

  - Basculez vers un pool de sauvegarde, puis restaurez le pool d’origine.

  - Basculez vers un pool de sauvegarde, créez un nouveau pool avec un nom de domaine complet différent (FQDN), puis importez les groupes de réponses dans le nouveau pool.

Lors de la phase de reprise après incident, les groupes de réponse résident dans plusieurs pools: dans le pool principal (non disponible) et dans le pool de sauvegarde. Les groupes Response dans les deux pools ont le même nom et le même propriétaire (le pool principal), mais ils ont des parents différents.

Lorsque vous récupérez en créant un nouveau pool avec un nom de domaine complet différent, vous devez affecter le nouveau pool en tant que propriétaire des groupes de réponses lorsque vous les importez. La propriété de Response Groups reste avec le pool d’origine à moins que vous ne le réactiviez explicitement à l’aide du paramètre-OverwriteOwner avec l’applet de certification **Import-CsRgsConfiguration** .

<div>


> [!NOTE]  
> Vous devez également utiliser le paramètre – OverwriteOwner si vous reconstruisez le pool lors de la récupération (autrement dit, la base de données du groupe de réponses est vide), que vous utilisiez ou non le même nom de domaine complet. Vous n’avez pas besoin d’utiliser le paramètre – OverwriteOwner si vous n’avez pas rérégénéré le pool, mais il est autorisé à utiliser ce paramètre chaque fois que vous importez les groupes de réponses vers le pool principal.



</div>

Vous ne pouvez définir qu’un ensemble de paramètres de configuration de groupe de réponse au niveau de l’application par liste. Il s’agit de la configuration par défaut de Music-Holding, du fichier audio de musique par défaut, de la période de grâce aux retours d’appel d’agent et de la configuration du contexte d’appel. Pour afficher ces paramètres de configuration, exécutez l’applet **de passe Get-CsRgsConfiguration** . Pour plus d’informations sur l’applet de connexion **Get-CsRgsConfiguration** , voir [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

Vous pouvez transférer ces paramètres au niveau de l’application d’un pool à un autre à l’aide de l’applet de passe **Import-CsRgsConfiguration** à l’aide du paramètre-ReplaceExistingSettings, mais cela a pour effet de remplacer les paramètres du pool de destination.

<div>


> [!IMPORTANT]  
> Cette contrainte concernant le transfert des paramètres vers un autre pool est vraie uniquement pour les paramètres au niveau de l’application et le fichier audio par défaut de musique. Cela ne s’applique pas aux groupes d’agents, files d’attente, flux de travail, heures d’activité et ensembles de jours fériés.



</div>

Si vous ne voulez pas remplacer les paramètres au niveau de l’application dans le pool de sauvegarde en cours de sinistre et que le pool principal ne peut pas être récupéré, les paramètres au niveau de l’application du pool principal seront perdus. Si vous avez besoin de créer un nouveau pool pour remplacer le pool principal lors de la récupération, avec le même nom de domaine complet ou un nom de domaine complet différent, vous ne pouvez pas récupérer les paramètres au niveau de l’application d’origine. Dans ce cas, vous devez configurer le nouveau pool avec ces paramètres et inclure le fichier audio de musique en attente.

Si vous décidez d’utiliser l’applet de cmdlet **Import-CsRgsConfiguration** pour transférer des paramètres au niveau de l’application à partir du pool principal vers le pool de sauvegarde en cours de sinistre, vous pouvez ensuite transférer les paramètres du pool de sauvegarde vers le nouveau pool lors de la récupération dans le même façon dont vous les avez transférés du pool principal vers le pool de sauvegarde.

Le tableau suivant est une vue d’ensemble des étapes nécessaires à la récupération de Response groups.

Pour plus d’informations sur l’exécution de ces étapes, voir [procédures de reprise après sinistre de Response Group dans Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### <a name="response-group-disaster-recovery-steps"></a>Étapes de la reprise après sinistre de Response Group

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
<td><p>Avant interruption</p></td>
<td><p>D’un point de vue régulier, exécutez l’applet de demande <strong>Export-CsRgsConfiguration</strong> pour créer des copies de sauvegarde de toutes les configurations de Response Group dans tous les pools frontaux dans lesquels l’application Response Group est déployée.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Pendant la période d’interruption</p></td>
<td><p>Exécutez l’applet de action <strong>Import-CsRgsConfiguration</strong> pour importer la configuration de service de groupe de réponses du serveur Lync</p>
<div>

> [!NOTE]  
> Utilisez le paramètre – ReplaceExistingSettings si vous voulez remplacer les paramètres du groupe de réponses au niveau de l’application dans le pool de sauvegarde par les paramètres de la liste principale. Si vous ne transférez pas les paramètres au niveau de l’application du pool principal vers le pool de sauvegarde et que le pool principal ne peut pas être récupéré, vous perdrez les paramètres du pool principal.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Après importation</p></td>
<td><p>Exécutez les applets de contrôle de Response Group avec le paramètre – ShowAll (pour afficher tous les groupes de réponse) ou le paramètre – Owner (pour afficher uniquement les groupes de réponse importés) pour vérifier que toutes les configurations de Response Group ont été importées dans le pool de sauvegarde.</p>
<div>

> [!IMPORTANT]  
> Si vous n’utilisez pas le paramètre – ShowAll ou – Owner, les groupes de réponse que vous avez importés dans le pool de sauvegarde ne seront pas répertoriés dans les résultats renvoyés par les applets de requête.


</div>
<p>Exécutez les applets de commande suivantes:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Après le basculement</p></td>
<td><ul>
<li><p>Passez un appel de test vers un groupe de réponse importé dans le pool de sauvegarde et vérifiez que l’appel est géré correctement.</p></li>
<li><p>Tous les agents officiels doivent se connecter à leur groupe formel sur le pool de sauvegarde.</p></li>
<li><p>Gérer les modifications de configuration:</p>
<p>Les groupes de réponses du pool de sauvegarde, qu’ils soient importés dans le pool de sauvegarde ou qui appartiennent au pool de sauvegarde, peuvent être modifiés comme d’habitude pendant la période d’interruption.</p>
<div>

> [!IMPORTANT]  
> Vous devez utiliser Lync Server Management Shell pour gérer les groupes de réponse que vous avez importés dans le pool de sauvegarde. Vous ne pouvez pas utiliser le panneau de configuration de Lync Server pour gérer ces groupes de réponse alors qu’ils se trouvent dans le pool de sauvegarde.


</div></li>
</ul></td>
<td><p>S/O</p></td>
</tr>
<tr class="odd">
<td><p>Après récupération, avant la restauration automatique</p></td>
<td><p>Exécutez l’applet de recherche <strong>Export-CsRgsConfiguration</strong> en spécifiant le paramètre-source en tant que pool de sauvegarde et le paramètre – owner comme pool principal pour exporter les groupes de réponse appartenant au pool principal du pool de sauvegarde.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Après la restauration automatique</p></td>
<td><ul>
<li><p>Exécutez l’applet de passe <strong>Import-CsRgsConfiguration</strong> pour importer les groupes de réponses dans le pool principal.</p>
<div>

> [!NOTE]  
> Si le pool principal ne peut pas être récupéré et que vous déployez un nouveau pool pour le remplacer, utilisez le paramètre – ReplaceExistingSettings pour transférer les paramètres au niveau de l’application du pool de sauvegarde vers le nouveau pool. Si vous ne transférez pas les paramètres à partir du pool de sauvegarde, le nouveau pool utilisera les paramètres par défaut.


</div></li>
<li><p>Exécutez les applets de commande suivantes à l’aide du paramètre – ShowAll (pour afficher tous les groupes de réponse) ou du paramètre – Owner (pour afficher uniquement les groupes de réponse importés) pour vérifier que toutes les configurations de Response Group ont été correctement importées dans le pool principal:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>Effectuez un test d’appel vers un groupe de réponse qui a été réimporté dans le pool principal, puis vérifiez que l’appel est géré correctement.</p></li>
<li><p>Vous pouvez également exécuter l’applet de commande <strong>Export-CsRgsConfiguration</strong> sur le pool de sauvegarde avec le paramètre – RemoveExportedConfiguration pour supprimer les groupes de réponse appartenant au pool principal du pool de sauvegarde.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

