# BindViewsExample
MOD06_DEMO_01

Creación de un modelo

    public class Restaurant
    {
        public int Id { get; set; }
        public string Name { get; set; }
        public string Address { get; set; }
        public bool Open { get; set; }
        public string Speciality { get; set; }
        public int Review { get; set; }
    }
    
Que será pasado a una vista Razor a través del controlador

 public class HomeController : Controller
    {
        public IActionResult Index()
        {
            Restaurant restaurant = new Restaurant() { Id = 1, Name = "My Kitchen 1", Address = "New Brunswick, 2657 Webster Street", Speciality = "Hamburgers", Open = true, Review = 4 };
            return View(restaurant);
        }

        [Route("Home/Display")]
        public IActionResult AnotherWayToDisplay()
        {
            Restaurant restaurant = new Restaurant() { Id = 2, Name = "My Kitchen 2", Address = "New Brunswick, 4175 Echo Lane Street", Speciality = "Sushi", Open = true, Review = 3 };
            return View(restaurant);
        }
    }
    
Y esta lo recogerá para mostrarlo


    <div>
        <p><b>Name</b>: @Model.Name</p>
        <hr />
        <p><b>Address</b>: @Model.Address</p>
        <hr />
        <p><b>Speciality</b>: @Model.Speciality</p>
        <hr />
        <p><b>Is Open</b>: @Model.Open</p>
        <hr />
        <p><b>Rating</b>: @Model.Review</p>
    </div>


