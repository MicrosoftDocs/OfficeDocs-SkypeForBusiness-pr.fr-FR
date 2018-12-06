---
title: "Résumé des certifi. - Féd. XMPP (Extensible Messaging and Presence Protocol)"
TOCtitle: "Résumé des certifi. - Féd. XMPP (Extensible Messaging and Presence Protocol)"
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49298562
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - Fédération XMPP (Extensible Messaging and Presence Protocol)

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les exigences de certificat pour l’activation et l’établissement de communications avec des partenaires XMPP (Extensible Messaging and Presence Protocol) requièrent l’enregistrement supplémentaire de vos domaines XMPP. L’enregistrement qui est inclus sur le certificat en tant qu’autre nom de l’objet (SAN) est le domaine pouvant participer aux communications XMPP. Ce domaine peut être le domaine de niveau racine (par exemple, contoso.com) si vous voulez activer XMPP pour l’ensemble de votre domaine, ou des domaines enfants sélectionnés (par exemple, corp.contoso.com, finance.contoso.com) si vous activez XMPP pour un sous-ensemble d’utilisateurs.

## Résumé du certificat pour le protocole XMPP


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant</th>
<th>Nom du sujet</th>
<th>Autres noms du sujet (SAN)/Ordre</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Assigner au service Edge d’accès du serveur Edge ou du pool de serveurs Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>Les trois premières entrées SAN correspondent aux entrées SAN normales d’un serveur Edge complet. L’entrée contoso.com correspond à l’entrée requise pour la fédération avec le partenaire XMPP au niveau du domaine racine. Cette entrée autorise le protocole XMPP pour tous les domaines affectés du suffixe contoso.com.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Tâches

[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Concepts

[Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  

#### Autres ressources

[Configuration des certificats de serveur Edge pour Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Request-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

