---
title: "Lync Server 2013 : Fonct. serveurs frontaux, mess. inst. et présence"
TOCTitle: Fonctionnalités de serveurs frontaux, de messagerie instantanée et de présence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398109(v=OCS.15)
ms:contentKeyID: 49296128
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fonctionnalités de serveurs frontaux, de messagerie instantanée et de présence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-17_

Les serveurs frontaux fournissent la plupart des fonctionnalités de Lync Server. Il existe deux éditions : Lync Server Enterprise Edition, qui est principalement conçue pour les grandes organisations, et Lync Server Standard Edition, qui est principalement conçue pour les petites organisations qui ne veulent pas faire de gros investissements en matériel et qui n’ont pas besoin d’une haute disponibilité. Les deux éditions prennent en charge toutes les charges de travail Lync Server, notamment la messagerie instantanée, la présence, les conférences et Voix Entreprise.

La messagerie instantanée permet aux utilisateurs de communiquer en temps réel les uns avec les autres sur leurs ordinateurs à l’aide des messages textuels.. Les sessions de messagerie unifiée à deux ou à plusieurs personnes sont prises en charge. Un participant à une conversation de messagerie instantanée peut ajouter un troisième participant à la conversation à tout moment. Lorsque cela arrive, la fenêtre Conversation change pour prendre en charge des fonctionnalités de conférence.

> [!IMPORTANT]  
> La communication un-à-un entre des clients Lync et Communicator est souvent désignée comme communication P2P. D’un point de vue technique, les deux clients communiquent via une conversation un-à-un, avec l’unité de contrôle multipoint Messagerie instantanée au milieu (composant du serveur frontal.) Le fait de placer celle-ci dans le flux de communication requis active l’enregistrement des détails des appels et d’autres fonctionnalités activées par le serveur frontal. La communication est établie entre un port source dynamique sur le client et le port TLS/TCP/5061 du serveur frontal (en supposant que le protocole TLS recommandé est utilisé). Par défaut, la communication P2P (ainsi que la messagerie instantanée entre plusieurs utilisateurs) n’est possible que lorsque Lync Server et l’unité de contrôle multipoint Messagerie instantanée sont actives et disponibles.

La *présence* fournit aux utilisateurs des informations sur l’état de présence des autres utilisateurs sur le réseau. Le statut de présence d’un utilisateur fournit des informations pour permettre aux autres utilisateurs de décider s’ils doivent essayer de contacter l’utilisateur et s’ils doivent pour cela utiliser la messagerie instantanée, le téléphone ou la messagerie électronique. La présence permet une communication instantanée lorsque cela est possible, mais fournit aussi des informations indiquant si un utilisateur est en réunion ou hors du bureau, indiquant que la communication instantanée n’est pas possible. L’état de présence est indiqué sous la forme d’une icône dans Lync et d’autres applications de présence, notamment le client de messagerie et de collaboration Microsoft Outlook, les logiciels Microsoft SharePoint, Microsoft Word et le tableur Microsoft Excel. L’icône de présence indique la disponibilité actuelle de l’utilisateur et sa volonté à communiquer.

