# bitrix.component.menu_sections
Компонент добавляет в меню секции и элементы (аналог стандартного компонента, но стандартный не добавляет элементы)<br>
Аналогичен стандартому, за исключением что можно выводить не только секции, но и элементы.<br>
Так же можно добавить заголовок к блоку ссылок.
Добавлена фильтрация разделов
<pre>
global $APPLICATION;
$aMenuLinksExt = $APPLICATION->IncludeComponent(
	"webit:menu.sections",
	"",
	Array(
		"TITLE" => "Заголовок",		// заголовок блока ссылок
		"IBLOCK_TYPE" => "iblock_type",
		"IBLOCK_ID" => "14",
		'FILTER' => [			// фильтр разделов
			'UF_SHOW_IN_MENU' => true
		],
		"INCLUDE_ALL_ELEMENTS" => "Y", //выводим в меню элементы
		"DEPTH_LEVEL" => "1",
		"CACHE_TYPE" => "A",
		"CACHE_TIME" => "3600"
	)
);

$aMenuLinks = array_merge($aMenuLinks, $aMenuLinksExt);
?>
</pre>
