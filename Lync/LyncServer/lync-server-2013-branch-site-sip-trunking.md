---
title: 'Lync Server 2013 : Jonction SIP de site de succursale'
TOCTitle: Jonction SIP de site de succursale
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412974(v=OCS.15)
ms:contentKeyID: 49298800
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Jonction SIP de site de succursale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Dans certains cas, il peut être nécessaire de mettre en place une jonction SIP distribuée à des sites de succursale. Pour déterminer si une jonction SIP est nécessaire pour un site de succursale, consultez les informations données dans [Implémentation d’une jonction SIP dans Lync Server 2013](lync-server-2013-how-do-i-implement-sip-trunking.md).

Pour plus d’informations sur les options de topologie prises en charge pour le déploiement de jonctions SIP dans un sites de succursale, reportez-vous à [Solutions de résistance de sites de succursale dans Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

## Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse

Au moment de prendre la décision de déployer une jonction SIP sur un site de succursale, vous devez effectuer une analyse de coût propre au site. Par exemple, une entreprise, dont le site central se trouve à Redmond (Washington) et le site de succursale se trouve à New York, doit effectuer une analyse pour déterminer s’il faut mettre en place une jonction SIP entre le site de New York et un fournisseur de services local.

Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe. Vous pouvez avoir un raccordement SDA pour le site de succursale au site central. Par exemple, le site central de Redmond peut héberger des numéros SDA pour le site de succursale de New York. Si le coût de mise en œuvre d’une jonction SIP distribuée est inférieur au coût de ces appels, envisagez de mettre en place une jonction SIP sur le site de succursale de New York.

## Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale

Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels RTC (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options. Si vous choisissez de déployer une jonction SIP sur un site de succursale, vous devez aussi déterminer la résistance et la bande passante nécessaires. Si la liaison entre votre site de succursale et votre site central est permanente et que la bande passante est suffisante, vous pouvez déployer une jonction SIP ou une passerelle. Il est alors inutile de déployer un Survivable Branch Appliance sur le site de succursale. Si la liaison entre le site de succursale et le site central n’est pas permanente, déployez un Survivable Branch Appliance ou un serveur Survivable Branch Server avec une passerelle ou une jonction SIP sur le site de succursale.

