---
title: "LS 2013 : Contr. d’adm. des appels avec passerelle RTC ou syst. PBX tiers"
TOCTitle: Contrôle d’admisson des appels avec une passerelle RTC ou un système PBX tiers
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398762(v=OCS.15)
ms:contentKeyID: 49298137
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Contrôle d’admisson des appels dans Lync Server 2013 avec une passerelle RTC ou un système PBX tiers

 

_**Dernière rubrique modifiée :** 2012-10-20_

Cette rubrique donne des exemples de déploiement du contrôle d’admission des appels sur la liaison entre l’interface de la passerelle du serveur de médiation et une passerelle RTC (réseau téléphonique commuté) ou un système PBX (Private Branch Exchange) tiers.

## Exemple 1 : Contrôle d’admission des appels entre le serveur de médiation et une passerelle RTC

Le contrôle d’admission des appels peut être déployé sur une liaison de réseau étendu depuis l’interface de la passerelle du serveur de médiation vers une passerelle RTC ou un système PBX tiers.

**Exemple 1 : Contrôle d’admission des appels entre le serveur de médiation et une passerelle RTC**

![Cas 1 : CAC entre passerelle PSTN de serveur de médiation](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Cas 1 : CAC entre passerelle PSTN de serveur de médiation")

Dans cet exemple, le contrôle d’admission des appels est appliqué entre le serveur de médiation et une passerelle RTC. Si un utilisateur de client Lync sur Site réseau 1 passe un appel RTC via la passerelle RTC dans Site réseau 2, le média circule via la liaison de réseau étendu. Par conséquent, deux vérifications de contrôle d’admission des appels sont effectuées pour chaque session RTC :

  - Entre l’application cliente Lync et le serveur de médiation

  - Entre le serveur de médiation et une passerelle RTC

Cet exemple s’applique aux appels RTC entrants vers un client dans Site réseau 1, ainsi qu’aux appels RTC sortants issus d’une application cliente dans Site réseau n1.

> [!NOTE]  
> Assurez-vous que le sous-réseau IP auquel appartient la passerelle RTC est configuré et associé au Site réseau 2.<br />
Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au Site réseau 1.<br />
Pour plus d’informations, reportez-vous à la section <a href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Association d’un sous-réseau à un site réseau dans Lync Server 2013</a>.

## Exemple 2 : Contrôle d’admission des appels entre le serveur de médiation et un système PBX tiers avec point de terminaison multimédia

Cette configuration est semblable à l’exemple 1. Dans les deux cas, le serveur de médiation connaît le périphérique qui arrête le média à l’extrémité opposée de la liaison de réseau étendu, et l’adresse IP de la passerelle RTC ou du PBX avec point de terminaison multimédia (MTP) est configurée sur le serveur de médiation comme tronçon suivant.

**Exemple 2 : Contrôle d’admission des appels entre le serveur de médiation et un système PBX tiers avec point de terminaison multimédia (MTP)**

![Cas 2 : CAC entre PBX de serveur de médiation avec MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Cas 2 : CAC entre PBX de serveur de médiation avec MTP")

Dans cet exemple, le contrôle d’admission des appels est appliqué entre le serveur de médiation et le PBX/MTP. Si un utilisateur de client Lync sur Site réseau n° 1 passe un appel RTC via le système PBX/MTP situé dans Site réseau n° 2, le média circule via la liaison de réseau étendu. Par conséquent, pour chaque session RTC, deux vérifications de contrôle d’admission des appels sont effectuées :

  - Entre l’application cliente Lync et le serveur de médiation

  - Entre le serveur de médiation et le système PBX/MTP

Cet exemple s’applique aux appels RTC entrants vers un client dans Site réseau n° 1, ainsi qu’aux appels RTC sortants issus d’un client dans Site réseau n° 1.

> [!NOTE]  
> Assurez-vous que le sous-réseau IP auquel appartient le MTP est configuré et associé au Site réseau 2.<br />
Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au Site réseau 1.<br />
Pour plus d’informations, reportez-vous à la section <a href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Association d’un sous-réseau à un site réseau dans Lync Server 2013</a>.

## Exemple 3 : Contrôle d’admission des appels entre le serveur de médiation et un système PBX tiers sans point de terminaison multimédia

L’exemple 3 est légèrement différent des deux premiers. Si le système PBX ne comporte aucun point de terminaison multimédia (MTP), le serveur de médiation ne sait pas où le média s’arrêtera dans les limites du PBX pour une demande de session sortante vers le PBX tiers. Dans ce cas, le média circule directement entre le serveur de médiation et le périphérique de point de terminaison tiers.

**Exemple 3 : Contrôle d’admission des appels entre le serveur de médiation et un système PBX tiers sans point de terminaison multimédia (MTP)**

![Cas 3 : CAC entre PBX de serveur de médiation sans MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Cas 3 : CAC entre PBX de serveur de médiation sans MTP")

Dans cet exemple, si un utilisateur de client Lync sur Site réseau n° 1 passe un appel à un utilisateur via le système PBX, le serveur de médiation est en mesure d’effectuer les vérifications de contrôle d’admission des appels sur le tronçon proxy uniquement (entre l’application cliente Lync et le serveur de médiation). Du fait que le serveur de médiation ne dispose pas d’informations sur le périphérique de point de terminaison quand la demande de session est effectuée, le contrôle d’admission des appels est impossible sur la liaison de réseau étendu (entre le serveur de médiation et le point de terminaison tiers) avant que l’appel soit établi. Une fois que la session est établie, toutefois, le serveur de médiation facilite la comptabilisation de la bande passante utilisée sur la jonction.

Pour les appels issus du point de terminaison tiers, les informations relatives à ce périphérique de point de terminaison sont accessibles au moment de la demande de session et le contrôle d’admission des appels peut s’effectuer des deux côtés du serveur de médiation.

> [!NOTE]  
> Assurez-vous que le sous-réseau IP auquel appartiennent les périphériques de point de terminaison est configuré et associé au Site réseau 2.<br />
Assurez-vous que le sous-réseau IP auquel appartiennent les deux interfaces du serveur de médiation est configuré et associé au Site réseau 1.<br />
Pour plus d’informations, reportez-vous à la section <a href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Association d’un sous-réseau à un site réseau dans Lync Server 2013</a>.
