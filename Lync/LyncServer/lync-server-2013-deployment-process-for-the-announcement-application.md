---
title: 'Lync Server 2013 : Processus de déploiement de l’application d’annonce'
TOCTitle: Processus de déploiement de l’application d’annonce
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398545(v=OCS.15)
ms:contentKeyID: 49297704
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de déploiement de l’application d’annonce dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit la procédure pour déployer l’application d’annonce. Vous devez déployer Voix Entreprise avant de configurer les annonces. Les composants requis par l’application d’annonce sont installés et déployés quand vous déployez Voix Entreprise.

### Processus de déploiement des annonces

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
<td><p><a href="lync-server-2013-create-an-announcement.md">Création d’une annonce dans Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configuration de la table des numéros non attribués dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Vérifier le déploiement de votre annonce</p></td>
<td><p>Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Facultatif) Vérification du déploiement des annonces dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

