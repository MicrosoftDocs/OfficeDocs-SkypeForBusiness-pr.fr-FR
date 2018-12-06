---
title: Exigences relatives au système DNS pour la mobilité
TOCTitle: Exigences relatives au système DNS pour la mobilité
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690040(v=OCS.15)
ms:contentKeyID: 49299097
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exigences relatives au système DNS pour la mobilité

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lorsque vous déployez la fonctionnalité de mobilité de Lync Server 2013, vous pouvez utiliser les nouvelles URL disponibles avec le service de découverte automatique de Lync Server 2013 ou utiliser vos URL de services web existantes. Si vous utilisez vos URL existantes, les utilisateurs doivent entrer manuellement les URL dans les paramètres de leur appareil mobile. Cette option est généralement utilisée à des fins de dépannage. Lorsque vous utilisez les nouvelles URL, les clients mobiles peuvent découvrir automatiquement les ressources Lync Server 2013. Lorsque vous prenez en charge la découverte automatique, vous devez ajouter de nouveaux enregistrements DNS (Domain Name System). Cette section décrit les enregistrements DNS nécessaires pour la découverte automatique.

Pour prendre en charge la découverte automatique, vous devez créer les enregistrements DNS suivants pour chaque domaine SIP :

  - un enregistrement DNS interne afin de prendre en charge les utilisateurs qui se connectent depuis le réseau de votre organisation ;

  - un enregistrement DNS externe, ou public, afin de prendre en charge les utilisateurs mobiles qui se connectent depuis Internet.

L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau. L’URL de découverte automatique externe ne doit pas être adressable depuis votre réseau. Toutefois, si cette condition ne peut pas être remplie pour l’URL externe, la fonctionnalité du client mobile ne devrait pas être affectée.

Les enregistrements DNS peuvent être des enregistrements CNAME ou des enregistrements A (hôte).

**Enregistrements DNS internes**

Vous devez créer l’un des enregistrements DNS internes suivants :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte ou définition SRV</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;domaine_sip&gt;</em></p></td>
<td><p>Nom de domaine complet des services Web internes pour votre pool de directeurs, si vous en avez un, ou pour votre pool de serveurs frontaux si vous n’avez pas de directeur</p></td>
</tr>
<tr class="even">
<td><p>A (hôte)</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;domaine_sip&gt;</em></p></td>
<td><p>Adresse IP interne des services Web (adresse IP virtuelle [VIP] si vous utilisez un programme d’équilibrage de la charge) de votre pool de directeurs, si vous en avez un, ou de votre pool de serveurs frontaux si vous n’avez pas de directeur.</p></td>
</tr>
</tbody>
</table>


**Enregistrements DNS externes**

Vous devez créer l’un des enregistrements DNS externes suivants :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;domaine_sip&gt;</em></p></td>
<td><p>Nom de domaine complet externe des services Web pour votre pool de directeurs, si vous en avez un, ou pour votre pool de serveurs frontaux si vous n’avez pas de directeur</p></td>
</tr>
<tr class="even">
<td><p>A (hôte)</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;domaine_sip&gt;</em></p></td>
<td><p>Adresse IP externe ou publique (adresse VIP si vous utilisez un programme d’équilibrage de la charge) du proxy inverse</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. <em>&lt;domaine_sip&gt;</em></p>
<p>Résout l’enregistrement d’hôte (A ou AAAA) pour le service Edge d’accès</p></td>
<td><p>Pour prendre en charge le service de notifications Push et le service de notifications Push Apple, vous créez un enregistrement SRV pour chaque domaine SIP ayant des clients Microsoft Lync Mobile.</p>
<div>

> [!IMPORTANT]  
> Cette condition s’applique uniquement aux clients Microsoft Lync Mobile sur des appareils mobiles Apple ou Microsoft. Les appareils Android et Nokia Symbian n’utilisent pas de notification push.
</div></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Le trafic Lyncdiscover, également appelé découverte automatique, traverse le proxy inverse. L’enregistrement SRV pointe sur un enregistrement résolu par le biais du service Edge d’accès.
