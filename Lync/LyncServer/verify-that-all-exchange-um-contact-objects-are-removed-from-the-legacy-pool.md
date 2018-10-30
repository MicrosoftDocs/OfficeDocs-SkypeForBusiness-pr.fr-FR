---
title: "Vérif. de la suppr. des objets de contact de mess. Un. Exchange du pool hérité"
TOCtitle: "Vérif. de la suppr. des objets de contact de mess. Un. Exchange du pool hérité"
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49891363
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification de la suppression des objets de contact de messagerie unifiée Exchange du pool hérité

 

_**Dernière rubrique modifiée :** 2012-09-26_

Utilisez l’outil **OCSUmUtil** ou l’applet de commande **Get-CsExumContact** pour vérifier que les objets contact de messagerie unifiée Exchange ont été supprimés du pool Office Communications Server 2007 R2 hérité. **OCSUmUtil** se trouve dans le dossier suivant :

%Program Files%\\Common Files\\ Lync Server 2013\\Support\\OcsUMUtil.exe

**OCSUmUtil** doit être exécuté à partir d’un compte d’utilisateur qui remplit les conditions suivantes :

  - appartenance aux groupes RTCUniversalServerAdmins et RTCUniversalUserAdmins (ce qui inclut les droits de lecture des paramètres de messagerie unifiée Exchange Server) ;

  - autorisations de domaine pour la création d’objets contact dans le conteneur d’unités d’organisation spécifié.

Pour plus d’informations sur l’utilisation de l’applet de commande **Get-CsExumContact**, reportez-vous à [Get-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact) dans la documentation Lync Server Management Shell.

