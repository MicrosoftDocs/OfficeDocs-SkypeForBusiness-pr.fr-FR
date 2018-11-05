---
title: Enregistrements DNS requis pour les serveurs de conversation permanente
TOCTitle: Enregistrements DNS requis pour les serveurs de conversation permanente
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205391(v=OCS.15)
ms:contentKeyID: 49299365
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enregistrements DNS requis pour les serveurs de conversation permanente

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit les enregistrements de service DNS (Domain Name Service) requis pour le déploiement de serveurs de conversations permanentes.

## Enregistrements DNS pour les serveurs de conversation permanente

Le tableau suivant recense les enregistrements DNS requis pour un déploiement serveur de conversations permanentes.

### Enregistrements DNS requis pour un serveur de conversation permanente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scénario de déploiement</th>
<th>Enregistrement DNS requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Un serveur de conversation permanente</p></td>
<td><p>Un enregistrement interne A qui associe le nom de domaine complet (FQDN) du serveur à son adresse IP.</p></td>
</tr>
<tr class="even">
<td><p>Pool de conversation permanente</p></td>
<td><p>Un enregistrement interne A qui associe le nom de domaine complet (FQDN) des serveurs à son adresse IP.</p>
<p><strong>Exemple</strong></p>
<p>PersistentChatServer01.contoso.com     10.10.10.1</p>
<p>PersistentChatServer02.contoso.com     10.10.10.2</p>
<p>Un enregistrement interne A qui associe le nom de domaine complet (FQDN) des serveurs à son adresse IP.</p>
<p><strong>Exemple</strong></p>
<p>PersistentChatPool.contoso.com    10.10.10.1</p>
<p>PersistentChatPool.contoso.com    10.10.10.2</p></td>
</tr>
</tbody>
</table>

