---
title: Configurer la base de données d’emplacements dans Lync Server 2013
TOCTitle: Configurer la base de données d’emplacements dans Lync Server 2013
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398679(v=OCS.15)
ms:contentKeyID: 49297949
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer la base de données d’emplacements dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-17_

Pour permettre aux clients de détecter automatiquement leur emplacement au sein d’un réseau, vous devez d’abord configurer la base de données d’emplacements. Si vous ne configurez pas de base de données d’emplacements et que l’option **Emplacement obligatoire** est définie sur **Oui** ou **Clause d’exclusion de responsabilité** dans la stratégie d’emplacement, l’utilisateur sera invité à entrer manuellement un emplacement.

Pour configurer la base de données d’emplacements, vous devrez effectuer les tâches suivantes :

1.  Remplir la base de données avec une correspondance des éléments réseau avec les emplacements. Si vous utilisez une passerelle ELIN (Emergency Location Identification Number), vous devez inclure le numéro ELIN dans le champ \<nomsociété\>.

2.  Valider les adresses par rapport à la base de données MSAG gérée par le fournisseur de service E9-1-1.

3.  Publier la base de données mise à jour.

> [!NOTE]  
> Vous pouvez également définir une base de données d’emplacements source secondaire pouvant être utilisée à la place de la base de données d’emplacements. Pour plus d’informations, voir <a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurer un service Informations d’emplacement secondaire</a>.

## Dans cette section

  - [Renseigner la base de données d’emplacements](lync-server-2013-populate-the-location-database.md)

  - [Valider les adresses](lync-server-2013-validate-addresses.md)

  - [Publier la base de données d’emplacements](lync-server-2013-publish-the-location-database.md)

