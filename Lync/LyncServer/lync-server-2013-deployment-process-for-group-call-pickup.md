---
title: Processus de déploiement de la prise d’appel de groupe
TOCTitle: Processus de déploiement de la prise d’appel de groupe
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945615(v=OCS.15)
ms:contentKeyID: 53095354
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de déploiement de la prise d’appel de groupe

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit la procédure de déploiement de la prise d’appel de groupe. Avant de configurer la réponse de groupe, vous devez déployer Enterprise Edition ou Standard Edition avec Voix Entreprise. Les composants requis par la réponse de groupe sont installés et activés quand vous déployez Voix Entreprise.

### Processus de déploiement de la prise d’appel de groupe

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
<th>Groupes et rôles requis</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Activer l’outil de kit de ressources SEFAUtil dans la topologie</p></td>
<td><ol>
<li><p>Utilisez l’applet de commande <strong>New-CsTrustedApplicationPool</strong> pour créer un pool d’applications approuvées.</p></li>
<li><p>Utilisez l’applet de commande <strong>New-CsTrustedApplication</strong> pour spécifier l’outil SEFAUtil comme application approuvée.</p></li>
<li><p>Exécutez l’applet de commande <strong>Enable-CsTopology</strong> pour activer la topologie.</p></li>
<li><p>Installez les outils de kit de ressources sur un serveur frontal faisant partie du pool d’applications approuvées créé à l’étape 1.</p></li>
<li><p>Vérifiez que l’outil SEFAUtil fonctionne correctement en l’exécutant pour afficher les paramètres de transfert d’appel d’un utilisateur dans le déploiement.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Déployer l’outil SEFAUtil</a></p></td>
</tr>
<tr class="even">
<td><p>Configurer les plages de numéros de prise d’appel dans la table des numéros d’appel parqué</p></td>
<td><p>Utilisez l’applet de commande <strong>New-CSCallParkOrbit</strong> pour créer des plages de numéros de prise d’appel dans la table des numéros d’appel parqué et affecter aux plages de prise d’appel le type GroupPickup.</p>

> [!NOTE]  
> Vous devez utiliser Lync Server Management Shell pour créer, modifier, supprimer et afficher des plages de numéros de prise d’appel de groupe dans la table des numéros d’appel parqué. Les plages de numéros de prise d’appel de groupe ne sont pas disponibles dans le Panneau de configuration Lync Server.


> [!NOTE]  
> Pour une intégration transparente aux plans de numérotation existants, les plages de numéros sont en général configurées en tant que bloc d’extensions virtuelles. Il n’est pas possible d’affecter des numéros SDA (sélection directe à l’arrivée, Direct Inward Dialing (DID)) comme numéros de plages dans la table des numéros d’appel parqué.

</td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurer des numéros de groupe de prise d’appel</a></p></td>
</tr>
<tr class="odd">
<td><p>Affecter un numéro de prise d’appel aux utilisateurs et activer la prise d’appel de groupe pour les utilisateurs</p></td>
<td><p>Utilisez le paramètre /enablegrouppickup dans l’outil de kit de ressources SEFAUtil pour activer la prise d’appel de groupe et affecter un numéro de prise d’appel pour les utilisateurs.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Activer la prise d’appel de groupe pour des utilisateurs et assigner un numéro de groupe</a></p></td>
</tr>
<tr class="even">
<td><p>Informer les utilisateurs du numéro de prise d’appel qui leur a été affecté et de tout autre numéro digne d’intérêt</p></td>
<td><p>Tout utilisateur pouvant récupérer un appel à destination d’un utilisateur de la prise d’appel de groupe, les utilisateurs peuvent souhaiter surveiller plusieurs groupes.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communiquer les affectations de prise d’appel de groupe aux utilisateurs</a></p></td>
</tr>
<tr class="odd">
<td><p>Vérifier le déploiement de la prise d’appel de groupe</p></td>
<td><p>Testez la réalisation et la récupération des appels pour vérifier que la configuration fonctionne comme prévu.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Facultatif) Vérifier le déploiement de la prise d’appel de groupe</a></p></td>
</tr>
</tbody>
</table>

